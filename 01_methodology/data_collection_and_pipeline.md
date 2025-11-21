# Data Collection and Processing Pipeline

## Overview

This document details the technical procedure used to extract, transform, and prepare data for network analysis in the study *"Inter-Organizational Collaborations in Open-Source Software Ecosystems"*.  
The steps below describe how repositories were downloaded, developer (node) and collaboration (edge) lists were created, loaded into a database, and processed for visualization and analysis in **Gephi**.

---

## 0. Repository Download from GitHub

### Purpose
Obtain complete and verifiable local copies of the open-source projects analyzed in this study.

### Repositories
The following GitHub repositories were cloned for analysis:

| Ecosystem  | Repository URL                            |
|------------|-------------------------------------------|
| React      | https://github.com/facebook/react         |
| Vue        | https://github.com/vuejs/core             |
| TensorFlow | https://github.com/tensorflow/tensorflow  |
| Bootstrap  | https://github.com/twbs/bootstrap         |
| Flutter    | https://github.com/flutter/flutter        |

### Command
Clone each repository using:

```bash
git clone --mirror https://github.com/<organization>/<repository>.git
```

The `--mirror` flag ensures a **complete copy** of all branches, tags, and commit metadata, including contributor history required for longitudinal analysis.

Alternatively, to minimize storage:
```bash
git clone --bare https://github.com/<organization>/<repository>.git
```

### Notes
- Cloning was performed between **January and March 2025**, ensuring snapshot consistency across all ecosystems.  
- All repositories were stored locally in the directory:
  ```
  /data/github_repos/<ecosystem_name>/
  ```
- No code modifications or commit rewrites were made.
- All further analyses (Steps 1-8) were conducted on these local clones.

---

## 1. Node List Creation

### Purpose
Generate a list of all unique contributors (developers or organizations) in a given GitHub repository.

### Command
```bash
git log --no-merges --pretty=format:'%an;%ae' | sort -u > XXXX_node.csv
```

### Description
- Extracts all commit authors (`%an`) and emails (`%ae`) excluding merge commits.
- Produces a clean list of contributors without duplicates.
- Each row represents one unique developer.


---

## 2. Edge List Creation

### Purpose
Construct a list of connections (edges) between developers who worked on the same files within the same project.

### Command
```bash
git log --name-only --no-merges --pretty=format:"%ad;%ae" --date=short | awk '{ for (n=1; n++<NF; ) print $1";"$n }' RS= FS=$'\n' > XXXX_edge.csv
```

### Description
- Logs all commits with corresponding author and affected file names.
- Generates temporal and relational edges linking contributors to files and collaborators.
- The resulting CSV represents co-edit relationships based on shared file edits.


---

## 3. Organization-Level Data Extraction

### Purpose
Aggregate developers by organizational domain to build inter-organizational networks.

### Node Command
```bash
git log --no-merges --pretty=format:'%an;%ae;%ad' --date=short | awk -F ';' '{split($2, domain, "@"); split(domain[2], company, "."); print $1";"$2";"company[1]";"$3}' | sort -u > XXXX_node.csv
```

This script:
- Splits the email domain (`@company.com`) to infer organizational affiliation.
- Adds the organization name as an additional column.
- Produces a `node.csv` with: *Name;Email;Organization;Date*.
- Manual corrections and verifications were applied where necessary.

### Post-Processing
Append a **type label** to classify each entry as a person node:

```bash
sed -i 's/$/;person/g' XXXX_node.csv
```

---

## 4. Project-Wise Processing

### Steps
1. Repeat **Steps 0-3** for each selected OSS project (React, Vue, TensorFlow, Bootstrap, Flutter).  
2. Store the generated node and edge files.
3. Ensure uniform headers across all files:
   - **Node List:** `ID,Name,Organization,Type`
   - **Edge List:** `Date,Source,Target`

---

## 5. Database Import

### Purpose
Centralize and persist data for query-based analysis.

### Process
1. Import node and edge CSVs into **MySQL** using tables:
   - `nodes (id, name, type, organization, date)`
   - `edges (source, target, project, date)`
2. Verify referential integrity (all edges must link existing nodes).
3. Run sanity checks on duplicates and disconnected nodes.

---

## 6. Gephi Processing Workflow

### Overview
Gephi was used for visualization, community detection, and metric computation.
Schematic construction process details -> schematic_construction_process_for_the_developer_and_company_network.pdf

### Workflow

#### Step 1 - Import Data
- **Nodes:** Import `XXXX_node.csv` -> columns: *ID, Name, Organization, Type*  
- **Edges:** Import `XXXX_edge.csv` -> columns: *Source, Target, Project, Date*

#### Step 2 - MultiMode Network Plugin
- Attribute: `Type`
- Left: *person-null*  
- Right: *null-person*
- Remove nodes and edges after processing  
=> Creates a pure developer-level projection.

#### Step 3 - Layout and Visualization
- Layout algorithm: **Yifan Hu**  
- Optimal distance: *200*  

#### Step 4 - Community and Appearance
1. In **Overview -> Appearance**, group by organization.  
2. In **Data Laboratory**, copy "organization" to "Label".  
3. Generate groups by definition.  
4. Apply **Yifan Hu layout** again for optimal separation.  
5. Edit labels (e.g., rename "Group of Alphabet" -> "Alphabet").  
6. Remove "None" entries.  
7. Add color coding via new column `ColorOfNode`.  
8. Apply color ranking:
   - Appearance -> Nodes -> Ranking -> Degree (1-50).

Result:  
Clean, color-coded organization-level collaboration networks for each OSS ecosystem.
=> Creates a pure organizational-level projection.

---

## 7. Output and Integration

- The resulting networks were exported as `.gephi` and `.pdf` files.
- Final metrics (degree, density, clustering, reciprocity, Gini) are included in:
  ```
  /Replication_Package_JSS/03_results/
  ```

---

## 8. Reproducibility Notes

- All scripts and commands are executable on Linux/macOS terminals.  
- No proprietary tools were used beyond Gephi (open source).  
- Parameters and filters (e.g., `--no-merges`, yearly slicing) are consistent across ecosystems.
- The entire process can be repeated from raw Git logs to final visualization following this documentation.
