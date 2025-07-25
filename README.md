# SAGA Attack Template Generation

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1VooWmsH5WA3y48S7N6PWRLX4GIyjQ8bb)

This project automates the generation of SAGA (Security Attack Graph and Analysis) attack templates from raw Procmon logs. It uses a Large Language Model (LLM) to identify and filter malicious system events, extracts behavioral patterns, and abstracts them into a structured, reusable JSON format.

## Key Features

-   **Log Preprocessing**: Cleans and standardizes raw Procmon CSV logs.
-   **Intelligent Event Filtering**: Uses a Gemini-powered LLM to identify and isolate suspicious events related to a specific attack command.
-   **Metadata Enrichment**: Maps attack behaviors to the MITRE ATT&CK® framework by looking up ability metadata.
-   **Automated Abstraction**: Generalizes specific event details (e.g., file paths, IPs) into broader categories.
-   **Template Generation**: Produces a structured JSON SAGA template that describes the attack's requirements, behaviors, and outcomes.

---

## Getting Started

The easiest way to run this project is by using the provided Google Colab notebook.

### Prerequisites

-   A Google Account
-   Your **Google API Key** for the Gemini model.

### Usage

1.  **Open the Notebook**: Click the **"Open in Colab"** badge above or use [this link](https://colab.research.google.com/drive/1VooWmsH5WA3y48S7N6PWRLX4GIyjQ8bb) to open the notebook directly in Google Colab.
2.  **Add Your API Key**: The notebook will require your `GOOGLE_API_KEY`. Follow the instructions in the notebook to add it using Colab's secret manager.
3.  **Run the Cells**: Execute the notebook cells in order from top to bottom.
4.  **Upload Data**: When prompted, upload your Procmon CSV log file. A sample log file is available in the `sample_data` directory of this repository.

The final SAGA template will be generated and saved to your Google Drive, in a folder specified within the notebook.

---

## Project Structure

While the entire workflow is contained in the Colab notebook, the repository is organized for clarity:

```
SAGA-Attack-Template-Generation/
├── README.md
├── notebooks/
│   └── SAGA_attack_template_generation.ipynb
└── sample_data/
    └── Exfiltrate_data_HTTPS_using_curl_windows.csv
```

-   **notebooks/**: Contains the main Google Colab notebook.
-   **sample\_data/**: Provides an example Procmon log for testing the notebook.
