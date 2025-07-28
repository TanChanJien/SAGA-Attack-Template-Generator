# SAGA Attack Template Generator

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1VqbcwkTl63KBENlrkie8QyaCDhSyWWpc)

> **A semi-automated system that accelerates the creation of SAGA attack pattern templates from raw Procmon logs. This tool uses a Large Language Model (LLM) to help expand the SAGA framework's coverage of MITRE ATT&CK® tactics.**

---

## Overview
This project provides a semi-automated system to accelerate the creation of SAGA attack pattern templates. It leverages the power of Google's Gemini Pro Large Language Model (LLM) to analyze raw Procmon logs and generate a ready-to-use Python (`.py`) template, significantly reducing the manual effort required to model adversary behaviors.

## Features
- **Auto Log Filtering**: Automatically processes and deduplicates raw Procmon logs to prepare them for analysis.
- **AI-Powered Rule Generation**: Uses Gemini to analyze log events and the original attack command to generate human-readable filtering rules that isolate the attack's footprint.
- **Automated Abstraction**: Detects and generalizes specific artifacts (file paths, process names) into SAGA-compliant hypernyms, requirements, and outcomes.
- **Python Template Output**: Generates a structured .py file containing the complete SAGA template, ready for final verification and use.
- **Zero-Setup Environment**: Runs entirely in Google Colab, requiring no local installation or dependency management.

## Workflow: Human-in-the-Loop
This system combines machine efficiency with expert oversight. The analyst performs the attack and provides the final validation, while the tool handles the intermediate data processing.


## Quick Start (Google Colab)
Get started in under a minute with just a few clicks.

1. **Click the Badge**: Open the notebook in Google Colab using the button above.
2. **Add API Key**: The notebook will prompt you to add your GOOGLE_API_KEY. Use Colab's "Secrets" manager for security.
3. **Upload & Run**: Upload your Procmon .CSV file and run all the cells (Runtime > Run all).
4. **Download Template**: Download the generated saga_template.py file from the Colab environment.

## Workflow
This tool transforms raw logs into a structured template through a multi-stage pipeline. The "Quick Start" runs this entire workflow, which includes crucial checkpoints for user verification.

1. **Log Ingestion & Preprocessing**: The notebook loads your Procmon CSV, cleans the data, and structures it for the AI to analyze.
2. **AI-Powered Rule Generation**: Gemini analyzes the events and suggests a set of rules to isolate the attack. You have the opportunity to review and edit these rules to ensure accuracy.
3. **Template Building & Abstraction**: With the approved rules, the system filters the logs and uses Gemini again to abstract the concrete details into SAGA's required format (hypernyms, requirements, outcomes).
4. **Python Template Generation**: Finally, the system assembles all the structured information into a complete `saga_template.py` file.

## Example Output
Here is a simplified example of what the tool produces at different stages.
### **Filtered Events (Example)**
B. **Generated Rules (Example)**
C. **Key Events `.json` (Example)**
D. **Generated Abstraction (Example)**
E. **Final Template `.py` (Example)**

## Requirements
All necessary Python libraries and dependencies are pre-installed in the Google Colab environment. You do not need to install anything on your local machine.

## Contributing
Contributions to this tool are welcome! If you have suggestions for improving the prompts, the processing logic, or the workflow, please feel free to open an issue or submit a pull request.

## Acknowledgements
This tool would not be possible without the foundational work and technologies from:
- The **SAGA framework** for providing the structured template model.
- The **MITRE ATT&CK® framework** for defining adversary behaviors.
- **Google Colab** for providing an accessible, zero-setup development environment.
- **Google's Gemini Pro** for its powerful language and reasoning capabilities.
