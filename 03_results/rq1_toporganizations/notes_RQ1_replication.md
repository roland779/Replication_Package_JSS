# Notes on Replication - RQ1: Top Organizations and Developer Participation

## Overview

This folder contains all datasets, figures, and (where applicable) tables supporting **Research Question 1 (RQ1)** of the study *"Inter-Organizational Collaborations in Open-Source Software Ecosystems"*.  
RQ1 examines how contributor composition and activity evolve over time, distinguishing between **organization-affiliated** and **volunteer (independent)** developers.

The analyses quantify (a) the number of active developers, (b) their respective shares of total commits, and (c) the concentration and strategic motivations of leading organizations.

---

## Data Source and Processing

All RQ1 results originate from the pipeline described in  
[`../../01_methodology/data_collection_and_pipeline.md`](../../01_methodology/data_collection_and_pipeline.md).

- Source data from **MySQL** tables: `developer`, `organization`, `commits_changelog`.  
- Developer categorization:  
  - **Organization developers** -> contributors with resolvable corporate domains.  
  - **Volunteer developers** -> contributors without a domain match.  
- Yearly aggregation for **2014-2023**.  
- Figure-level datasets are provided to reproduce each visualization.

---

## File Structure

```
rq1_toporganizations/
├── figures/
│   ├── Figure_2_Volunteer_Developer_vs_Organizational_Developer.pdf
│   ├── Figure_3_Volunteer_Developer_vs_Organizational_Developer_Commits.pdf
│   └── Figure_4_Lorenz_Curve.pdf
│   └── Figure_5_Strategic_Motivations_from_Top_Contributing_Organizations.pdf
│
├── data/
│   ├── Figure_2_Volunteer_Developer_vs_Organizational_Developer_Data.xlsx
│   ├── Figure_3_Volunteer_Developer_vs_Organizational_Developer_Commits.xlsx     
│   ├── Figure_4_Lorenz_Curve_Organizations_Data.xlsx
│   └── Figure_5_Strategic_Motivations_from_Top_Contributing_Organizations.pptx
│
├── tables/
│   ├── Table_4_Basic_Network_Metrics_Organization.xlsx                             
│   └── Table_4_Basic_Network_Metrics_Organization.csv                        
│
└── notes_RQ1_replication.md
```

> **Note:** For long-term accessibility and reuse, CSV counterparts of Excel tables are recommended (see `tables/`).

---

## Figures and Tables

### **Figure 2 - Volunteer vs. Organizational Developers (2014-2023)**  
**Figure:** `figures/Figure_2_Volunteer_Developer_vs_Organizational_Developer.pdf`  
**Data:** `data/Figure_2_Volunteer_Developer_vs_Organizational_Developer_Data.xlsx`  

Shows the yearly number of active developers by affiliation. Organizational participation increases over time, indicating stronger corporate engagement in OSS ecosystems.

**Axes:** Year (2014-2023) x Number of Developers.

---

### **Figure 3 - Commit Shares by Developer Type (2014-2023)**  
**Figure:** `figures/Figure_3_Volunteer_Developer_vs_Organizational_Developer_Commits.pdf`  
**Data:** `data/Figure_3_Volunteer_Developer_vs_Organizational_Developer_Commits.xlsx` 

Depicts relative commit contributions of organizational vs. volunteer developers. The trend shows increasing institutionalization of OSS participation.

**Axes:** Year (2014-2023) x Percentage of Commits (0-100%).

---

### **Figure 4 - Lorenz Curve of Organizational Contributions (2014-2023)**  
**Figure:** `figures/Figure_4_Lorenz_Curve.pdf`  
**Data:** `data/Figure_4_Lorenz_Curve_Organizations_Data.xlsx`  

Illustrates inequality of contributions among organizations. Gini-like concentration indicates that a small number of firms account for the majority of commits.

**Axes:** Cumulative Normalized Rank of Organizations x Cumulative Normalized Share of Commits.

---

### **Figure 5 - Strategic Motivations of Top Contributing Organizations**  
**Supplementary:** `data/Figure_5_Strategic_Motivations_from_Top_Contributing_Organizations.pptx`  

Summarizes qualitative evidence on the strategic motivations of key firms (e.g., IBM, Alphabet, AMD, Nvidia, Intel, MobileIron), visualized as a radar chart (stability, compatibility, security, innovation, performance, AI/ML orientation).

---

### **Table 4 - Basic Network Metrics (2014-2023)**  
**Table:** `tables/Table_4_Basic_Network_Metrics_Organization.xlsx`
**Open format:** `tables/Table_4_Basic_Network_Metrics_Organization.csv`   

Descriptive SNA metrics per year: nodes, edges, average degree, density. These values quantify structural evolution and support cross-ecosystem comparisons.

---

## Validation and Reproducibility
 
- All figures reproducible directly from the provided figure-level datasets in `/data/`.  
- Consistent definitions and naming conventions across datasets.  
- Figures/tables correspond to Section 5.1 / **RQ1** in the manuscript.  
- CSV counterparts are encouraged for open, tool-agnostic reuse (R/Python).

---

*Prepared by Roland Robert Schreiber (November 2025) for inclusion in the replication package accompanying the revised manuscript submitted to the *Journal of Systems and Software (JSS).*