# Notes on Replication - 02_data: Raw Exports, Processed Networks, and Validation

## Overview

This directory provides the **complete dataset layer** supporting all analyses and figures in the paper *"Inter-Organizational Collaborations in Open-Source Software Ecosystems."*  
It includes the raw Git-based data extractions, processed network datasets, and validation materials for five OSS ecosystems:  
**React, Vue, TensorFlow, Bootstrap, and Flutter.**

Observation period: **2014-2023**.

---

## Data Source and Processing

All data were extracted and processed following the workflow documented in  
[`../01_methodology/data_collection_and_pipeline.md`](../01_methodology/data_collection_and_pipeline.md).
[`../01_methodology/schematic_construction_process_for_the_developer_and_company_network.pdf`](../01_methodology/schematic_construction_process_for_the_developer_and_company_network.pdf).

**Extraction:**  
- `git log` exports for each repository clone.  
- Data elements: commit hash, author name, email, timestamp, and changed files.  

**Preprocessing:**  
- Normalization of contributor names and email domains.  
- Classification into **organization-affiliated** vs. **volunteer** developers.  
- Yearly segmentation by commit timestamps (2014-2023).  
- Aggregation into standardized node and edge CSV files.  

All commit-level data originate from **public GitHub repositories** under **GitHub's Terms of Service**.  
No private, restricted, or anonymized data were included.

---

## File Structure

```
02_data/
├── 01_raw_git_exports/
│   ├── oss_bootstrap_2014-2023_nodes.csv
│   ├── oss_bootstrap_2014-2023_edges.csv
│   ├── oss_flutter_2014-2023_nodes.csv
│   ├── oss_flutter_2014-2023_edges.csv
│   ├── oss_react_2014-2023_nodes.csv
│   ├── oss_react_2014-2023_edges.csv
│   └── ...
│
└── 02_processed_logs/
    ├── Developer_2014-2023_Edges.csv
    ├── Developer_2014-2023_Nodes.csv
    ├── Organization_2014-2023_Edges.csv
    └── Organization_2014-2023_Nodes.csv
```

> **Note:** All CSV files use UTF-8 encoding, `,` as delimiter, and `.` as decimal separator.

---

## Subfolder 01_raw_git_exports

Contains the **raw Git-based node and edge exports** for each ecosystem covering the years 2014-2023.

| Variable | Type        | Example / Unit               | Description                                 |
|----------|-------------|------------------------------|---------------------------------------------|
| `id`     | String      | `usr_0458`                   | Unique developer or organization identifier |
| `Name`   | String      | `"Mueller"`                  | Node label (name)                           |
| `type`   | Categorical | `"person"`, `"organization"` | Node category                               |
| `orga`   | String      | `"Alphabet"`                 | Organization affiliation if resolvable      |
| `project`| String      | `"Flutter"`                  | Project                                     |
| `date`   | Date        | `"2025-11-03"`               | Recorded commit                             |
| `source` | String      | `usr_0458`                   | Source node (for edges)                     |
| `target` | String      | `org_0007`                   | Target file commit                          |

---

## Subfolder 02_processed_networks

Contains **aggregated and merged network datasets** derived from the raw exports.  
These files are used for network metric computation, figure generation, and cross-case comparisons.

| File                               | Description                                                         |
|------------------------------------|---------------------------------------------------------------------|
| `Developer_2014-2023_Nodes.csv`    | Consolidated node developer list across all ecosystems and years    |
| `Developer_2014-2023_Edges.csv`    | Combined developer edge list for all ecosystems                     |
| `Organization_2014-2023_Nodes.csv` | Consolidated node organization list across all ecosystems and years |
| `Organization_2014-2023_Edges.csv` | Combined organization edge list for all ecosystems                  |

Example Mapping:
Developer 1 (Organization 1a) -> File A; Project X
Developer 2 (Organization 2b) -> File A; Project X
Developer 1 -> File B; Project XY

Developer 1 - Developer 2
Organization 1a - Organization 2b

=> [`../01_methodology/schematic_construction_process_for_the_developer_and_company_network.pdf`](../01_methodology/schematic_construction_process_for_the_developer_and_company_network.pdf).
 
Each file follows the same column definitions as in the raw exports, but aggregates data across ecosystems or years.

---

## Validation and Reproducibility

- Node and edge counts were cross-checked against repository statistics for each ecosystem.  
- Random samples of affiliation mappings manually verified (n ≈ 500).  
- Duplicates removed via normalized author-email combinations.  
- All datasets are fully machine-readable and reusable.

---

## License and Reuse

- Derived datasets released under **Creative Commons Attribution 4.0 (CC BY 4.0)**.  
- Original Git commit metadata remain under **GitHub's Terms of Service**.  
- No personal or private data included.  
- When reusing or extending this dataset, please cite:  
  *Schreiber, R.R. & Wieland, T. (2025). Inter-Organizational Collaborations in Open-Source Software Ecosystems. Journal of Systems and Software.*

---

*Prepared by Roland Robert Schreiber (November 2025)*  
*Replication Package - JSSOFTWARE-D-25-00781*
