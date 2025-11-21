# Replication Package - Journal of Systems and Software (JSS)

**Manuscript ID:** JSSOFTWARE-D-25-00781  
**Title:** *Inter-Organizational Collaborations in Open-Source Software Ecosystems*  
**Authors:** Roland Robert Schreiber, Thomas Wieland  
**Version:** 1.0 (November 2025)  
**Corresponding Paper Version:** Revised submission to JSS  

---

## 1. Purpose and Context

This replication package accompanies the revised manuscript submitted to the *Journal of Systems and Software (JSS)* in November 2025.  
It provides all data, exports, figures, and methodological documentation required to verify and reproduce the empirical results presented in the paper.

The study investigates patterns and dynamics of **inter-organizational collaboration** within five major open-source software (OSS) ecosystems hosted on GitHub:
**React, Vue, TensorFlow, Bootstrap, and Flutter.**

All commit-related data (usernames, emails, timestamps) were retrieved from publicly available GitHub repositories under GitHub's Terms of Service. 
The dataset contains no private or non-public information. Following established OSS research practices, no additional anonymization was applied.

The package follows the *JSS Reproducibility Guidelines* and documents the complete workflow - from raw Git-based data extraction and network analysis to longitudinal and comparative visualization. All replication materials are shared under the CC BY 4.0 license.

---

## 2. Structure Overview

```text
Replication_Package_JSS/
│
├── 01_methodology/
│   ├── data_collection_and_pipeline.md
│   ├── replication_guidelines_JSS_compliance.md
│   └── schematic_construction_process_for_the_developer_and_company_network.pdf
│
├── 02_data/
│   ├── 01_raw_git_exports/
│   ├── 02_processed_logs/
│   └── notes_data_replication.md
│
├── 03_results/
│   ├── rq1_toporganizations/
│   │   ├── notes_RQ1_replication.md
│   ├── rq2_interorganizational_collaboration/
│   │   ├── notes_RQ2_replication.md
│   ├── rq3_evolution_collaboration/
│   │   ├── notes_RQ3_replication.md
│   └── rq4_coopetition_networks/
│       ├── notes_RQ4_replication.md
│
└── LICENSE.txt
```

---

## 3. Replication Steps

Detailed documentation of all methodological steps can be found in  
`/01_methodology/data_collection_and_pipeline.md`.

### Step 0 - Repository Download  
Clone the five public GitHub repositories using `git clone --mirror`.  
All repositories were cloned between **January and March 2025** to ensure consistent snapshots.

### Step 1 - Node and Edge List Creation  
Contributor and co-edit relationships were extracted using `git log`, `awk`, and `sed`.  
Edge lists reflect file-based co-edit relationships between contributors.

### Step 2 - Organization Mapping  
Affiliations were inferred from contributor email domains and validated manually.  
This process created a linkage between developers and organizations.

### Step 3 - Database Integration  
All extracted data were imported into a **MySQL 8.0** database.  
All tables use **UTF8MB4 encoding**.

### Step 4 - Network Visualization  
Networks were visualized with **Gephi 0.10** using the **Yifan Hu** layout algorithm.  
MultiMode and Ego Network plugins were applied where appropriate.

### Step 5 - Longitudinal and Cross-Case Analysis  
Comparative and temporal analyses across the five OSS ecosystems were conducted, supported by metrics such as network density, degree centralization, reciprocity, and Gini coefficient.

### Step 6 - Validation and Reproducibility  
Cross-verification between Gephi metrics, data storage, and manual affiliation checks ensures full reproducibility.

---

## 4. Research Questions and Corresponding Results

### **RQ1 - Top Organizations and Developer Participation**  
**Folder:** `/03_results/rq1_toporganizations/`  
Analyzes the growth of organization-affiliated versus volunteer developers (2014-2023).  
Includes Figures 2-5 and Table 4.  
See: `notes_RQ1_replication.md`

---

### **RQ2 - Collaboration Patterns across OSS Ecosystems**  
**Folder:** `/03_results/rq2_interorganizational_collaboration/`  
Examines inter-organizational and developer-level collaboration networks across ecosystems.  
Includes Figures 6-7 and corresponding `.gephi` network files.  
See: `notes_RQ2_replication.md`

---

### **RQ3 - Evolution of Inter-Organizational Collaboration**  
**Folder:** `/03_results/rq3_evolution_collaboration/`  
Analyzes how network structures evolve over time using longitudinal snapshots (2014-2023).  
Includes Figure 8 and Table 6.  
See: `notes_RQ3_replication.md`

---

### **RQ4 - Organizational Coopetition in OSS Ecosystems**  
**Folder:** `/03_results/rq4_coopetition_networks/`  
Focuses on how major organizations (Alphabet, Meta, IBM, AMD, etc.) simultaneously collaborate and compete.  
Includes Figure 9 (a-h) and eight ego-network `.gephi` files.  
See: `notes_RQ4_replication.md`

---

## 5. Mapping of Results to Manuscript

| Research Question | Folder                                              | Corresponding Figures / Tables |
|-------------------|-----------------------------------------------------|--------------------------------|
| RQ1               | `03_results/rq1_toporganizations/`                  | Figures 2-5, Table 4           |
| RQ2               | `03_results/rq2_interorganizational_collaboration/` | Figure 6-7                     |
| RQ3               | `03_results/rq3_evolution_collaboration/`           | Figure 8, Table 6              |
| RQ4               | `03_results/rq4_coopetition_networks/`              | Figure 9                       |

---

## 6. Software and Environment

| Component         | Version                              | Purpose                                |
|-------------------|--------------------------------------|----------------------------------------|
| Python            | 3.11                                 | Data preprocessing and metric analysis |
| MySQL             | 8.0                                  | Data storage and querying              |
| Gephi             | 0.10                                 | Network visualization and metrics      |
| Git               | 2.43+                                | Repository extraction                  |
| awk / sed         | latest                               | Log parsing and transformation         |
| OS Environment    | Windows / macOS / Linux compatible   | Operating system                       |
| Charset           | UTF8MB4                              | Support for Unicode developer names    |

---

## 7. Data Source and Ethical Use

All datasets included in this replication package are derived from **publicly available GitHub repositories**  
(*React*, *Vue*, *TensorFlow*, *Bootstrap*, *Flutter*).  

No private repositories, forks, or enterprise datasets were accessed.  
All commit metadata (author names, emails, timestamps) are publicly available under GitHub's Terms of Service.  

The replication package complies with the Journal of Systems and Software data availability policy, providing fully shared data, code, and documentation for complete reproducibility.


---

## 8. Citation

If you use this replication package, please cite:

> Schreiber, R.R., & Wieland, T. (2025).  
> *Inter-Organizational Collaborations in Open-Source Software Ecosystems.*  
> Journal of Systems and Software, Revision Manuscript ID: JSSOFTWARE-D-25-00781.

---

## 9. Contact

**Roland Robert Schreiber**  
University of Bamberg  
roland-robert.schreiber@stud.uni-bamberg.de  

**Thomas Wieland**  
Coburg University of Applied Sciences  
thomas.wieland@hs-coburg.de  

---

## 10. Version Information

- Replication Package Version: **1.0**  
- Corresponding Paper Version: Revised submission to JSS  
- Last Modified: **08 November 2025**

---

*This replication package fulfills the Journal of Systems and Software reproducibility requirements and adheres to Elsevier's data sharing and ethical use policies.*
*The replication materials are distributed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).*
