# Notes on Replication - RQ3: Temporal Evolution of Inter-Organizational Collaboration

## Overview

This folder contains all datasets, figures, and network files supporting **Research Question 3 (RQ3)** of the study *"Inter-Organizational Collaborations in Open-Source Software Ecosystems"*.  
RQ3 analyzes how inter-organizational collaboration structures evolve over time, based on longitudinal network snapshots and associated quantitative metrics.

---

## Data Source and Temporal Segmentation

All RQ3 data were extracted from the MySQL tables `sna_nodes_organizations` and `sna_edges`, covering the period **2014-2023**.  
Networks were segmented into five two-year intervals to capture temporal evolution:

1. **2014-2015** 2. **2016-2017** 3. **2018-2019** 4. **2020-2021** 5. **2022-2023**

Each network snapshot represents collaboration relationships between organizations based on co-editing activities within the five OSS ecosystems (**React**, **Vue**, **TensorFlow**, **Bootstrap**, **Flutter**).

---

## File Structure

```
rq3_evolution_collaboration/
├── figures/
│   └── Figure_8_Evolution_Organizations_summary.pdf
│
├── data/
│   ├── Figure_8_Evolution_Organizations_details.pptx
│   └── Figure_8_Evolution_Organizations_details.pdf
│
├── tables/
│   ├── Table_6_Basic_Network_Metrics_Organization.xlsx
│   └── Table_6_Basic_Network_Metrics_Organization.csv
│
└── networks/
    ├── Figure_8_2014_Organization_Collaboration_gephi.gephi
    ├── Figure_8_2014_Organization_Collaboration_nodes.csv
    ├── Figure_8_2014_Organization_Collaboration_edges.csv
    ├── Figure_8_2016_Organization_Collaboration_gephi.gephi
    ├── Figure_8_2016_Organization_Collaboration_nodes.csv
    ├── Figure_8_2016_Organization_Collaboration_edges.csv
    ├── Figure_8_2018_Organization_Collaboration_gephi.gephi
    ├── Figure_8_2018_Organization_Collaboration_nodes.csv
    ├── Figure_8_2018_Organization_Collaboration_edges.csv
    ├── Figure_8_2020_Organization_Collaboration_gephi.gephi
    ├── Figure_8_2020_Organization_Collaboration_nodes.csv
    ├── Figure_8_2020_Organization_Collaboration_edges.csv
    ├── Figure_8_2022_Organization_Collaboration_gephi.gephi
    ├── Figure_8_2022_Organization_Collaboration_nodes.csv
    └── Figure_8_2022_Organization_Collaboration_edges.csv
```

---

## Figures and Tables

### **Figure 8 - Evolution of Inter-Organizational Collaboration**
**Figures:**  
- `figures/Figure_8_Evolution_Organizations_details.pdf`  
- `figures/Figure_8_Evolution_Organizations_summary.pdf`  
- `data/Figure_8_Evolution_Organizations_details.pptx`  

**Networks (with raw data):**  
- `.gephi` files - full network visualizations for each two-year period  
- `.csv` files - corresponding node and edge lists for each network snapshot  

**Description:**  
Visualizes the temporal evolution of inter-organizational collaboration networks.  
Node size indicates **degree centrality**, while color denotes **community clusters**.  
The summary figure provides an overview of structural transitions, and the detailed figure presents individual time windows (a–e) showing the growth, consolidation, and stabilization of collaboration patterns.

---

### **Table 6 - Basic Network Metrics (2014-2023)**  
**Table:**  
- `tables/Table_6_Basic_Network_Metrics_Organization.xlsx`  
- `tables/Table_6_Basic_Network_Metrics_Organization.csv`  

**Description:**  
Presents quantitative changes in network characteristics across all time intervals, including **nodes**, **edges**, **average degree**, and **density**.  
The `.csv` version provides an open, long-term accessible format for direct analytical reuse in R, Python, or Gephi.

---

## Validation and Reproducibility

- Networks constructed from public GitHub commit data using the same extraction pipeline as RQ1-RQ2.  
- Edge weights correspond to the frequency of shared file edits between organizations.  
- Temporal segmentation validated using commit timestamps.  
- Node and edge `.csv` files exported directly from the `.gephi` project files for transparency and reusability.  
- All `.gephi` files can be reopened in **Gephi v0.10** to reproduce Figures 8 (a-e).  
- Quantitative metrics cross-checked with Gephi-calculated values and stored in both `.xlsx` and `.csv` formats.  
- Figures correspond to Section 5.3 / RQ3 in the manuscript.

---

## Notes on Raw Data

All `.gephi`, `.csv`, and table files constitute the **raw data** for this analysis.  
Each dataset contains complete node and edge information for the corresponding time period, allowing independent reproduction, secondary analyses, and validation of longitudinal collaboration trends.  
Providing both human-readable (Excel) and machine-readable (CSV) formats ensures compliance with *JSS* open-data and long-term reproducibility standards.

---

*Prepared by Roland Robert Schreiber (November 2025)* for inclusion in the replication package accompanying the revised manuscript submitted to the *Journal of Systems and Software (JSS).*
