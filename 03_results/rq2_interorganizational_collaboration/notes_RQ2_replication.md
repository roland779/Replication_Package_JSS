# Notes on Replication - RQ2: Inter-Organizational Collaboration Across OSS Ecosystems

## Overview

This folder contains all datasets, figures, and network files supporting **Research Question 2 (RQ2)** of the study *"Inter-Organizational Collaborations in Open-Source Software Ecosystems"*.  
RQ2 investigates collaboration structures among developers and organizations across five major open-source ecosystems: **React**, **Vue**, **TensorFlow**, **Bootstrap**, and **Flutter**.

The analyses explore how inter-organizational connections shape collaboration, how network density and centralization differ between ecosystems, and how firms co-develop within shared software infrastructures.

---

## Data Source and Processing

All RQ2 materials are derived from the data pipeline described in  
[`../../01_methodology/data_collection_and_pipeline.md`](../../01_methodology/data_collection_and_pipeline.md).

- Data originate from the public Git commit histories of the five OSS ecosystems.  
- Nodes represent **developers** (individual contributors), and edges indicate **co-edit relationships** (joint file edits).  
- Developer-organization mappings were derived from verified email domains and manually validated.  
- Networks were visualized and analyzed in **Gephi v0.10** using the **Yifan Hu** layout algorithm.  
- Metrics such as network density, average degree, and degree centralization were calculated for each ecosystem.  

All relevant artifacts are structured as follows:

```
rq2_interorganizational_collaboration/
├── figures/
│   ├── Figure_6_Overview_Developer_OSS_Ecosystems.pdf
│   ├── Figure_7_SNA_Organizations.pdf
│
├── data/
│   ├── Figure_6_Overview_Developer_OSS_Ecosystems.pptx
│   ├── Figure_7_SNA_Organizations.pptx
│
└── networks/
    ├── Figure_6_Overview_Developer_OSS_gephi.gephi
    ├── Figure_6_Overview_Developer_OSS_nodes.csv
    ├── Figure_6_Overview_Developer_OSS_edges.csv
    ├── Figure_7_SNA_Organizations_gephi.gephi
    ├── Figure_7_SNA_Organizations_nodes.csv
    └── Figure_7_SNA_Organizations_edges.csv
```

---

## Figures

### **Figure 6 - Developer Collaboration Across OSS Ecosystems**  
**Figure:** `figures/Figure_6_Overview_Developer_OSS_Ecosystems.pdf`  
**Source:** `data/Figure_6_Overview_Developer_OSS_Ecosystems.pptx`  
**Network:** `networks/Figure_6_Overview_Developer_OSS_gephi.gephi`  
**Raw data:** `networks/Figure_6_Overview_Developer_OSS_nodes.csv`, `networks/Figure_6_Overview_Developer_OSS_edges.csv`  

**Description:**  
Compares developer-level collaboration networks for five OSS ecosystems (**TensorFlow**, **React**, **Flutter**, **Bootstrap**, **Vue**).  
Each node represents a developer; edges indicate co-edits on shared files.  
The networks reveal ecosystem-specific structural differences, highlighting density variations and distinct core-periphery structures.

---

### **Figure 7 - Inter-Organizational Collaboration Structures**  
**Figure:** `figures/Figure_7_SNA_Organizations.pdf`  
**Source:** `data/Figure_7_SNA_Organizations.pptx`  
**Network:** `networks/Figure_7_SNA_Organizations_gephi.gephi`  
**Raw data:** `networks/Figure_7_SNA_Organizations_nodes.csv`, `networks/Figure_7_SNA_Organizations_edges.csv`  

**Description:**  
Shows the collaboration networks between major contributing organizations (e.g., Alphabet, IBM, AMD, Nvidia, Intel, Meta, MobileIron).  
Edges represent joint developer contributions to shared files or modules.  
The visualization illustrates collaboration intensity, centralization, and cross-firm interdependencies within OSS development ecosystems.

---

## Validation and Reproducibility

- Developer-organization mappings validated through manual domain inspection.  
- Node and edge CSVs exported directly from the `.gephi` project files.  
- Cross-verification performed between `.gephi` metrics and MySQL queries.  
- All visualizations reproducible using Gephi layout settings described above.  
- Figures correspond to Section 5.2 / RQ2 in the manuscript.  

---

*Prepared by Roland Robert Schreiber (November 2025)* for inclusion in the replication package accompanying the revised manuscript submitted to the *Journal of Systems and Software (JSS).*
