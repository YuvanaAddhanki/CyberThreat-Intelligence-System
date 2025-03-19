# AI-Powered Real-Time Cyber Threat Intelligence System

## Project Overview
Cyberattacks are evolving rapidly, and traditional security systems struggle to detect and analyze threats in real-time. This project introduces an AI-powered cyber threat intelligence system that leverages Retrieval-Augmented Generation (RAG) to provide real-time threat detection, classification, and retrieval of past attack patterns.

## Features
- Real-Time Threat Intelligence: Fetches and processes live security data from cybersecurity APIs.
- AI-Powered Threat Classification: Uses pre-trained AI models (DistilBERT) to classify threats.
- Vector Database for Retrieval: Stores and retrieves historical cyberattack patterns using FAISS.
- Automated Security Alerts: Notifies teams of potential threats via email, Slack, or Telegram.
- FastAPI Deployment: Provides an API for security teams to analyze and retrieve threats.

## Technologies Used
- Python
- FastAPI (for REST API deployment)
- Pathway (for real-time data processing)
- FAISS (for vector-based threat retrieval)
- Transformers (DistilBERT for AI threat classification)
- Uvicorn (server deployment)
- Requests (fetching data from cybersecurity APIs)

## Project Structure
```
├── main.py              # Main FastAPI application
├── threat_db.py         # FAISS-based threat database
├── ai_model.py          # AI-powered threat classification
├── data_ingestion.py    # Fetching real-time cybersecurity data
├── pathway_pipeline.py  # Real-time threat processing with Pathway
├── requirements.txt     # Dependencies
└── README.md            # Documentation
```

## Installation & Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/cyber-threat-intelligence.git
   cd cyber-threat-intelligence
   ```
2. Create a virtual environment (recommended):
   ```bash
   python -m venv env
   source env/bin/activate  # On macOS/Linux
   env\Scripts\activate  # On Windows
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## How to Run the Project
1. Start the FastAPI server:
   ```bash
   uvicorn main:app --host 0.0.0.0 --port 8000 --reload
   ```
2. Access the API at: `http://localhost:8000/docs`
3. Test API Endpoints:
   - `POST /analyze_threat` - Analyze an IP address for threats.
   - `GET /search_threat` - Retrieve past threat intelligence from FAISS.

## Example API Request
```bash
curl -X 'POST' \
  'http://localhost:8000/analyze_threat' \
  -H 'Content-Type: application/json' \
  -d '{ "ip": "8.8.8.8" }'
```

## Real-Time Threat Intelligence Sources
- VirusTotal API – Scans files & URLs for malware.
- Shodan API – Detects exposed IoT devices & vulnerable servers.
- HaveIBeenPwned API – Checks for leaked credentials & data breaches.

## Future Enhancements
- Improve AI model accuracy with fine-tuned transformers.
- Expand support for additional cybersecurity APIs.
- Deploy in cloud environments like AWS Lambda or GCP.
- Integrate with enterprise SOCs and SIEM systems.

## Conclusion
This project provides a scalable, real-time cybersecurity intelligence system that enhances security operations by combining AI, real-time threat processing, and historical retrieval. By leveraging Pathway and FAISS, organizations can proactively detect and mitigate threats efficiently.

Developed by ClueLessCoders
