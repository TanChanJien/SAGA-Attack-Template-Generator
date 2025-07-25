# SAGA Attack Template Generator

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://your-colab-link-here)

> **A semi-automated system that accelerates the creation of SAGA attack pattern templates from raw Procmon logs. This tool uses a Large Language Model (LLM) to help expand the SAGA framework's coverage of MITRE ATT&CK® tactics.**

---

## The Challenge: The Manual Bottleneck
The SAGA framework relies on a diverse library of attack patterns to generate realistic synthetic audit logs. However, creating these templates manually is a time-consuming, labor-intensive process that involves sifting through thousands of log entries to isolate and abstract key attack behaviors. This bottleneck slows down the expansion of the SAGA dataset, especially for under-represented tactics.

## Our Solution: LLM-Powered Acceleration
This project streamlines the template creation process by using a Large Language Model (LLM) to automate the most tedious steps. It takes a raw Procmon CSV log from a simulated attack and produces a draft SAGA template that is ready for final human verification. By handling the heavy lifting of event filtering and abstraction, this tool shortens the template creation time from hours to minutes.

## Workflow: Human-in-the-Loop
This system combines machine efficiency with expert oversight. The analyst performs the attack and provides the final validation, while the tool handles the intermediate data processing.

*(You can insert the workflow diagram here)*

## Getting Started
The entire workflow is contained within a Google Colab notebook.

1.  **Simulate and Capture**: Perform an attack action in a controlled environment and capture the system events using Procmon, saving the output as a CSV file.
2.  **Open the Notebook**: Click the "Open in Colab" badge at the top of this README.
3.  **Configure**: When the notebook loads, add your `GOOGLE_API_KEY` to the Colab secrets manager as prompted.
4.  **Upload and Run**: Upload your Procmon CSV file and run the cells in order.
5.  **Verify Rules**: The system will first generate a set of human-readable rules to filter events. **This is a critical checkpoint.** Review and edit these rules in the notebook to ensure they accurately represent the attack.
6.  **Generate and Refine**: Continue running the cells to produce the final SAGA JSON template. Manually inspect the output file for correctness and logic before submitting it to the SAGA project.

## Contributing
Contributions to this tool are welcome! If you have suggestions for improving the prompts, the processing logic, or the workflow, please feel free to open an issue or submit a pull request.

## Acknowledgements
This work is built upon the concepts and framework introduced in the original SAGA paper. For more details on the SAGA framework, please refer to:

* Yi-Ting Huang, et al. **SAGA: Synthetic Audit Log Generation for APT Campaigns**. arXiv:2411.13138v1, Nov 2024.
