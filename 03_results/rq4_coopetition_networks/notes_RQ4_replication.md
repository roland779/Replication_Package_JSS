# Notes on Replication - RQ4: Organizational Coopetition (Ego Networks of Major Firms)

## Overview

This folder contains all artifacts supporting **Research Question 4 (RQ4)** of the study *"Inter-Organizational Collaborations in Open-Source Software Ecosystems"*.  
RQ4 focuses on **coopetition** by examining **ego networks** of leading organizations - where a focal firm (e.g., Alphabet, Meta, Nvidia, Intel, IBM, AMD, MobileIron, TensorFlow) is the ego and connected alters are partner organizations linked via shared development activity.

The analyses characterize how competing firms simultaneously **collaborate and compete** across ecosystems, and how their local network structures (ties, clustering, centrality) reveal strategic positioning.

---

## Data Source and Processing

All RQ4 ego networks were derived from the Git-based extraction and organization mapping pipeline described in  
[`../../01_methodology/data_collection_and_pipeline.md`](../../01_methodology/data_collection_and_pipeline.md).

- **Nodes** represent organizations; **edges** represent collaboration ties based on **co-edit relationships** (shared file edits).  
- For each focal firm, the **ego network** includes the ego, its direct neighbors (alters), and edges among them.  
- Networks were analyzed in **Gephi v0.10** using the **Yifan Hu** layout; node size encodes **degree centrality**; colors denote **communities**.  
- All `.gephi` files are accompanied by **open `.csv` raw data** (node and edge lists) for full reusability.

---

## File Structure

```
rq4_coopetition_networks/
├── figures/
│   └── Figure_9_Ego_Organization_Network_Analysis_details.pdf        
│
├── data/
│   └── Figure_9_Ego_Organization_Network_Analysis_details.pptx
│
└── networks/
    ├── Figure_9__a_Alphabet_Orga_Ego_Network.gephi
    ├── Figure_9__a_Alphabet_Orga_Ego_Network_nodes.csv
    ├── Figure_9__a_Alphabet_Orga_Ego_Network_edges.csv

    ├── Figure_9__b_TensorFlow_Orga_Ego_Network.gephi
    ├── Figure_9__b_TensorFlow_Orga_Ego_Network_nodes.csv
    ├── Figure_9__b_TensorFlow_Orga_Ego_Network_edges.csv

    ├── Figure_9__c_Meta_Orga_Ego_Network.gephi
    ├── Figure_9__c_Meta_Orga_Ego_Network_nodes.csv
    ├── Figure_9__c_Meta_Orga_Ego_Network_edges.csv

    ├── Figure_9__d_Nvidia_Orga_Ego_Network.gephi
    ├── Figure_9__d_Nvidia_Orga_Ego_Network_nodes.csv
    ├── Figure_9__d_Nvidia_Orga_Ego_Network_edges.csv

    ├── Figure_9__e_Intel_Orga_Ego_Network.gephi
    ├── Figure_9__e_Intel_Orga_Ego_Network_nodes.csv
    ├── Figure_9__e_Intel_Orga_Ego_Network_edges.csv

    ├── Figure_9__f_MobileIron_Orga_Ego_Network.gephi
    ├── Figure_9__f_MobileIron_Orga_Ego_Network_nodes.csv
    ├── Figure_9__f_MobileIron_Orga_Ego_Network_edges.csv

    ├── Figure_9__g_IBM_Orga_Ego_Network.gephi
    ├── Figure_9__g_IBM_Orga_Ego_Network_nodes.csv
    ├── Figure_9__g_IBM_Orga_Ego_Network_edges.csv

    └── Figure_9__h_AMD_Orga_Ego_Network.gephi
        Figure_9__h_AMD_Orga_Ego_Network_nodes.csv
        Figure_9__h_AMD_Orga_Ego_Network_edges.csv
```

> **Note:** CSV filenames follow the pattern `<figure-id>_<firm>_nodes.csv` and `<figure-id>_<firm>_edges.csv`.


---

## Figures

### **Figure 9 - Ego Networks of Major Contributing Organizations (Panels a-h)**
**Figure(s):**  
- `figures/Figure_9_Ego_Organization_Network_Analysis.pdf`  
- `data/Figure_9_Ego_Organization_Network_Analysis_details.pptx`

**Networks (with raw data):**  
- Alphabet -> `networks/Figure_9__a_Alphabet_Orga_Ego_Network.*`  
- TensorFlow -> `networks/Figure_9__b_TensorFlow_Orga_Ego_Network.*`  
- Meta -> `networks/Figure_9__c_Meta_Orga_Ego_Network.*`  
- Nvidia -> `networks/Figure_9__d_Nvidia_Orga_Ego_Network.*`  
- Intel -> `networks/Figure_9__e_Intel_Orga_Ego_Network.*`  
- MobileIron -> `networks/Figure_9__f_MobileIron_Orga_Ego_Network.*`  
- IBM -> `networks/Figure_9__g_IBM_Orga_Ego_Network.*`  
- AMD -> `networks/Figure_9__h_AMD_Orga_Ego_Network.*`

**Description:**  
Each panel displays an organization-centered view of collaboration ties (ego + alters).  
Edge thickness corresponds to **tie strength** (frequency of shared file edits).  
The panels reveal persistent **coopetitive relationships** (e.g., Alphabet-Meta-Nvidia) and differences in local centralization and community overlap indicative of strategic partnering.

---

## Validation and Reproducibility

- Ego networks generated from the same Git-based pipeline as RQ1-RQ3 with manual validation of organization mappings.  
- For each ego network, `.gephi` files are provided together with **raw `.csv` node and edge lists**.  
- Layout parameters (Gephi v0.10, **Yifan Hu**) and visual encodings (size = degree, color = community) are consistent across panels.  
- Figures correspond to Section 5.4 / RQ4 in the manuscript.

---

## Notes on Raw Data

Providing both the `.gephi` project files and the corresponding `.csv` node/edge lists ensures **long-term accessibility**, **tool-agnostic reuse** (R/Python), and **transparent verification** of ego-level structures.  
These artifacts enable independent recalculation of local metrics (ego degree, clustering, effective size, constraint) and replication of coopetitive patterns reported in the paper.

---

*Prepared by Roland Robert Schreiber (November 2025)* for inclusion in the replication package accompanying the revised manuscript submitted to the *Journal of Systems and Software (JSS).*