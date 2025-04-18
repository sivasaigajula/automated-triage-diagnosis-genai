# Patient Triage and Diagnosis System

This repository contains the **Patient Triage and Diagnosis System**, a generative AI-powered solution to automate patient triage and diagnosis in healthcare settings. The system leverages Google's Gemini-2.0-Flash and Text-Embedding-004 models to process patient symptoms, vitals, and medical history, delivering fast, accurate, and data-driven insights for clinicians.

## Project Overview

The **Patient Triage and Diagnosis System** addresses challenges in healthcare, such as overloaded emergency departments, static medical databases, and manual triage processes. It uses generative AI to:

- **Triage Patients**: Assigns priorities (Emergent, Urgent, Non-urgent) based on symptoms, vitals, and history.
- **Predict Cardiovascular Risk**: Estimates long-term risk using age, blood pressure, and history.
- **Diagnose Conditions**: Generates structured diagnoses with confidence scores and recommended actions.
- **Analyze Symptom Similarity**: Compares symptoms to known conditions, visualized in a chart.
- **Track Patient History**: Maintains an Electronic Health Record (EHR) store.
- **Support Multi-Language Output**: Delivers results in languages like Spanish.
- **Present Results**: Renders outputs in a styled HTML/CSS report with cards, a table, and a chart.

The system fetches real-time medical knowledge from credible sources (`.edu`, `.gov`, `.org`) using the Google Search Tool, ensuring up-to-date diagnoses. It is implemented as a Jupyter Notebook [patient_triage_diagnosis.ipynb](https://www.kaggle.com/code/sivasai98/patient-triage-diagnosis-using-genai) and is suitable for clinical, research, or educational use.

Read the detailed project write-up on Medium: Automating Patient Triage and Diagnosis with Generative AI.

Explore the notebook on Kaggle: Patient Triage & Diagnosis using GenAI.

## Features

- **Generative AI Capabilities**:
  - Structured JSON output for diagnoses.
  - Function calling for triage and risk scoring.
  - Retrieval Augmented Generation (RAG) with internet-sourced medical knowledge.
  - Embeddings and vector search for symptom similarity analysis.
- **Styled Output**: Professional HTML/CSS report with cards, a responsive table, and a symptom similarity chart.
- **Multi-Language Support**: Translates outputs to languages like Spanish.
- **Robust Error Handling**: Includes retry policies and fallback mock data for API failures.

## Architecture Diagrams

The system’s architecture is visualized through the following diagrams:

### Flowchart
<img src="https://raw.githubusercontent.com/sivasaigajula/automated-triage-diagnosis-genai/refs/heads/main/Images/FlowChart.png" alt="Flow Chart" width="500"/>

<p>High-level architecture showing components like user input, GenAI services, and output layer.</p>

### Sequence Diagram
<img src="https://raw.githubusercontent.com/sivasaigajula/automated-triage-diagnosis-genai/refs/heads/main/Images/SequenceDiagram.png" alt="Sequence Diagram" />
<p>Data flow from user input through knowledge retrieval, GenAI processing, and output formatting. </p>

### Class Diagram
<img src="https://raw.githubusercontent.com/sivasaigajula/automated-triage-diagnosis-genai/refs/heads/main/Images/ClassDiagram.png" alt="Class Diagram" width="500"/>
<p> Interactions between GenAI components like Input Processor, Diagnosis Generator, and Report Renderer. </p>

## Installation

### Prerequisites

- Python 3.8+
- Jupyter Notebook or JupyterLab
- Google Cloud account with access to the Google Generative AI API

### Setup

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/sivasaigajula/automated-triage-diagnosis-genai.git
   cd automated-triage-diagnosis-genai
   ```

2. **Install Dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

   The `requirements.txt` includes:

   ```
   google-generativeai
   numpy
   pandas
   matplotlib
   ipython
   ```

3. **Set Up Google API Key**:

   - Obtain a Google Generative AI API key from Google Cloud Console.
   - If you don't already have an API key, you can grab one from [AI Studio](https://aistudio.google.com/app/apikey). You can find [detailed instructions in the docs](https://ai.google.dev/gemini-api/docs/api-key).

   - Set it as an environment variable:

     ```bash
     export GOOGLE_API_KEY='your-api-key'
     ```

   - Alternatively, configure it in the notebook:

     ```python
     import os
     os.environ["GOOGLE_API_KEY"] = "your-api-key"
     ```

4. **Verify Installation**:

   ```python
   import google.generativeai
   print(google.generativeai.__version__)  # Should print version (e.g., 0.8.2)
   ```

## Usage

1. **Open the Notebook**:

   ```bash
   jupyter notebook patient_triage_diagnosis.ipynb
   ```

2. **Run All Cells**:

   - Execute the cells in order to initialize the system, process patient data, and generate outputs.
   - The final cell (Cell 12) processes an example case with:
     - Symptoms: "chest pain, shortness of breath, history of hypertension"
     - Vitals: Heart rate 110, blood pressure 140/90
     - Age: 35
     - Language: Spanish

3. **View Outputs**:

   - **HTML Report**: Displayed in the notebook with cards, a symptom similarity table, and a chart.
   - **JSON Diagnosis**: Printed for debugging.

4. **Customize Inputs**:

   - Modify the example inputs in Cell 12 (e.g., change symptoms, vitals, or language).

   - Example:

     ```python
     patient_data = "40yo female, fever, cough"
     vitals = {"heart_rate": 90, "blood_pressure": "120/80"}
     age = 40
     patient_id = "patient-002"
     language = "English"
     ```


## References

- **[Medium Article](https://sivasaigajula.medium.com/automating-patient-triage-and-diagnosis-with-generative-ai-378b9db2d0cf)**: Automating Patient Triage and Diagnosis with Generative AI
- **[Kaggle Notebook](https://www.kaggle.com/code/sivasai98/patient-triage-diagnosis-using-genai)**: Patient Triage & Diagnosis using GenAI


## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m "Add YourFeature"`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a Pull Request.
