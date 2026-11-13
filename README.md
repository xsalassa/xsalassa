# Hi, I'm Xosya

Data engineering and workflow automation, with Python, SQL, and Google Cloud.

I build and maintain data pipelines, reporting workflows, and operational automation using Python, SQL, and Google Cloud. My work includes data transformation and validation, file generation and delivery, and monitoring integrations. The case studies below highlight selected examples I can share publicly.

## Engineering case studies

These write-ups use inspected source code, my articles and project documentation, with diagrams and selected sanitized source captures. The watermark study also shows a locally tested reconstruction with synthetic input. The cloud-flow write-ups do not claim verified deployments.

- [Excel generation with Airflow, Pub/Sub and Cloud Run](docs/case-studies/dynamic-reporting.md): publish workbook requests, query BigQuery and write XLSX in a worker, then check outputs and publish notification requests. A separate direct CSV/manifest DAG is documented alongside it.
- [Daily monitoring setup with Apps Script](docs/case-studies/monitoring-file-setup.md): prepare daily checkpoint workbooks, resolve weekday and holiday assignments, preserve existing files, and coordinate scheduled and manual monitoring checks.
- [Daily project updates with Power Automate](docs/case-studies/daily-project-report.md): turn an Excel checklist into a Teams summary, email report, and monthly activity log.
- [File approvals and report distribution](docs/case-studies/report-distribution.md): route incoming files through approval, workbook updates, and notifications.
- [SQL-to-Excel synchronization](docs/case-studies/sql-excel-sync.md): compare source and workbook records, update matching rows, and build notification tables.
- [PDF watermarking with Python and Power Automate Desktop](docs/case-studies/pdf-watermarking.md): apply an image overlay to PDFs through a desktop batch workflow, with clear limits on what the overlay proves.

## Tools used in these examples

| Work | Tools |
| --- | --- |
| File generation and orchestration | Apache Airflow, Python, BigQuery, Cloud Storage, Pub/Sub, Cloud Run, XlsxWriter |
| Spreadsheet automation | Google Apps Script, Google Sheets, Google Drive |
| Workflow integration | Power Automate, Excel Online, OneDrive, Teams, Outlook, SQL Server |
| Desktop document processing | Power Automate Desktop, Python, PyMuPDF |

## Selected AI & analytics projects

| Project | What to inspect |
| --- | --- |
| [Wanderlust Concierge (private repository)](https://github.com/xsalassa/buildwithgemini-wanderlust-concierge) | A travel-agent prototype using Google ADK, Gemini, Firestore, memory hooks and an A2UI frontend. Weather responses are simulated; live integrations depend on environment configuration. |
| [Quantium retail analytics](https://github.com/xsalassa/Quantium) | Python notebooks for customer segmentation, control-store selection and store-trial comparisons. Educational analysis with stored outputs; results have not been independently revalidated here. |
| [Plant disease classification](https://github.com/xsalassa/Klasifikasi-Penyakit-Tanaman) | Academic leaf-image classification experiments with CNN notebooks and saved evaluation figures. These are historical model experiments, with no new accuracy or deployment claim. |

These projects complement the six engineering case studies above. Their repository documentation distinguishes implemented code, prototypes and reproduction limits.

## Earlier SQL projects

My public repositories also include educational work:

- [Sales Performance Report](https://github.com/xsalassa/Sales-Performance-Report): retail sales and promotion analysis using DQLab material.
- [Customer Analytics](https://github.com/xsalassa/Customer-Analytics-Report---SQL): exercises on revenue, customer activity, and repeat transactions.
- [DQLab](https://github.com/xsalassa/DQLab): SQL, Python, and R learning exercises.

## How I document a project

I start with the input and the expected output, then explain the dependencies and the recovery path. If a result has not been measured or a demo cannot be reproduced, I say so.

[How to read the diagrams and source captures](docs/visuals.md)

[Browse my repositories](https://github.com/xsalassa?tab=repositories)
