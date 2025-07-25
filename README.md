# SAGA Attack Template Generator

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1VqbcwkTl63KBENlrkie8QyaCDhSyWWpc)

This project provides a semi-automated system to accelerate the creation of SAGA attack pattern templates from raw Procmon logs. It uses a Large Language Model (LLM) to analyze and abstract system events, significantly reducing the manual effort required to generate new templates.

[cite_start]The primary goal is to help expand the SAGA framework's coverage, especially for under-represented MITRE ATT&CK® tactics like **Initial Compromise**, **Lateral Movement**, and **Exfiltration**[cite: 4, 11, 49, 170].

## The Challenge

[cite_start]The SAGA framework relies on a diverse library of attack pattern templates to generate realistic, high-quality synthetic audit logs[cite: 185]. However, creating these templates manually from raw system logs is a time-consuming and labor-intensive process. A security analyst must:

1.  Execute a specific attack ability and capture the logs.
2.  Manually sift through thousands of events to isolate the few that are relevant to the attack.
3.  Abstract specific artifacts (e.g., file names, IP addresses) into generalized SAGA descriptors.
4.  Structure this information into the correct SAGA JSON format.

This manual bottleneck slows down the expansion of the SAGA dataset.

## Our Solution

This template generation system streamlines the process by leveraging Google's Gemini LLM to automate the most tedious steps. It takes a raw Procmon CSV log from a simulated attack and produces a draft SAGA template, ready for final human verification.

While not fully automated, this tool shortens the template creation time from hours to minutes, allowing contributors to focus on high-level validation rather than low-level data processing.

## Workflow

The system follows a semi-automated workflow that combines machine efficiency with expert oversight:

1.  **Simulate & Capture**: A user performs an attack action in a controlled environment and captures the system events using Procmon.
2.  **Ingest & Analyze**: The Colab notebook ingests the raw CSV log. The LLM analyzes the events alongside the original attack command to identify the most relevant event sequences.
3.  [cite_start]**Abstract & Generalize**: The LLM proposes abstractions for the key artifacts, generating the necessary `requirements`, `hypernyms`, and `outcomes` required by the SAGA template structure[cite: 248].
4.  **Generate Draft Template**: The system combines the filtered events and abstractions into a complete, structured JSON template.
5.  **Verify & Refine**: The user performs a final review of the generated template to ensure its accuracy and logic before submitting it to the SAGA project.

## How to Use

1.  **Open the Notebook**: Click the **"Open in Colab"** badge above.
2.  **Configure**: Add your `GOOGLE_API_KEY` to the Colab secrets manager as prompted.
3.  **Upload & Run**: Upload your Procmon CSV file and run the cells in order.
4.  **Verify Rules**: The notebook will first generate a set of human-readable rules that filter the events. Review and edit these rules as needed.
5.  **Generate Template**: Continue running the cells to produce the final SAGA JSON template.
6.  **Final Check**: Manually inspect the output JSON file for correctness before use.
