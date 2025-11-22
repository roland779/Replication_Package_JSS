# Replication Guidelines - JSS Data Availability and Reproducibility Compliance Summary

**Manuscript ID:** JSSOFTWARE-D-25-00781  
**Title:** *Inter-Organizational Collaborations in Open-Source Software Ecosystems*  
**Author:** Roland Robert Schreiber, Thomas Wieland

---

## 1. Reproducibility Statement

This replication package fulfills the **highest level of reproducibility** described in the *Journal of Systems and Software (JSS) Data Availability and Research Data Policy*, corresponding to a state in which **data, code, and documentation are fully shared and reusable**.


---

## 2. Data Availability

- **Data Source:** Public GitHub repositories (*React*, *Vue*, *TensorFlow*, *Bootstrap*, *Flutter*)  
- **Data Type:** Commit logs, developer affiliations, and co-edit relationships  
- **License:** Publicly available under GitHub's Terms of Service  
- **Ethical Compliance:** The package includes public personal data (developer names and email addresses) contained in Git commit metadata. These data are publicly available under GitHub's Terms of Service. Reuse must comply with applicable data protection regulations. 
- **Data Formats:** `.xlsx`, `.csv`, `.gephi`, `.pdf`, `.pptx`, `.md`

---

## 3. Documentation Completeness

| Component                      | Description                                       | Status             |
|--------------------------------|---------------------------------------------------|--------------------|
| Methodology                    | `/01_methodology/data_collection_and_pipeline.md` | checked            |
| Raw Data                       | `/02_data/notes_data_replication.md`              | checked            |
| Replication Notes per RQ (1-4) | `/03_results/RQ*/notes_RQ*_replication.md`        | checked            |
| Main README                    | `/00_README.md`                                   | checked            |
| LICENSE                        | `/LICENSE.txt`                                    | checked            |

---

## 4. Data and Code Accessibility

| Format    | Purpose                                   | Software                       |
|-----------|-------------------------------------------|--------------------------------|
| `.gephi`  | Network structure and visualization       | Gephi 0.10                     |
| `.xlsx`   | Network metrics and aggregated statistics | Excel / LibreOffice            |
| `.csv`    | Tabular raw data                          | Text-based, UTF-8 encoded      |
| `.pptx`   | Visualization templates                   | PowerPoint / LibreOffice       |
| `.pdf`    | Portable Document Format Visualization    | platform-independent           |
| `.md`     | Documentation                             | Markdown, platform-independent |

---

## 5. Verification and Validation

- All network metrics (density, degree centralization, clustering coefficient) were verified.  
- Developer-organization mappings validated manually (8 % sample).  
- Layouts and statistics generated deterministically (no randomization).  
- Figures 2-9 reproducible from provided data and Gephi project files.  
- All documentation written in English with UTF-8 encoding.

---

## 6. Ethical and Legal Compliance

- All data originate from publicly available GitHub repositories.  
- No private repositories, forks, or personal data used.  
- Full compliance with GitHub's Terms of Service and FAIR principles (*Findable, Accessible, Interoperable, Reusable*).

---

## 7. Compliance Summary

This replication package provides transparent, reusable data and documentation and thereby meets the **highest reproducibility level recognized by JSS**.
---

*Prepared by Roland Robert Schreiber (November 2025)* for inclusion in the replication package accompanying the revised manuscript submitted to the *Journal of Systems and Software (JSS)*.
