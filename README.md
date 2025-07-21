# Google Cloud Certifications Chatbot 🤖☁️

A Streamlit-powered chatbot that helps users with questions about Google Cloud certifications, leveraging Gemini AI and BigQuery Vector Search.

![Chatbot Demo](https://via.placeholder.com/800x400?text=Google+Cloud+Certifications+Chatbot+Demo) *(Replace with actual screenshot)*

## Features ✨

- **AI-Powered Q&A**: Get accurate answers about Google Cloud certifications
- **Knowledge Base**: Built from official Google Cloud exam guides
- **Semantic Search**: Finds relevant information using vector embeddings
- **User-Friendly Interface**: Simple Streamlit web interface
- **Cloud-Native**: Fully integrated with Google Cloud services

## Supported Certifications 📚

Currently includes resources for:
- Associate Cloud Engineer
- Professional Cloud Security Engineer

*(Easily extendable to other certifications)*

## Tech Stack 🛠️

| Component               | Technology Used          |
|-------------------------|-------------------------|
| Frontend                | Streamlit               |
| LLM                     | Google Gemini           |
| Vector Database         | BigQuery Vector Search  |
| Embeddings              | Vertex AI text-embedding-005 |
| Backend Framework       | LangChain               |
| Cloud Platform          | Google Cloud Platform   |

## Prerequisites 📋

Before you begin, ensure you have:

1. **Google Cloud Account** with:
   - Billing enabled
   - Vertex AI API enabled
   - BigQuery API enabled

2. **Python 3.9+** installed

3. **Google Cloud SDK** installed and configured

## Setup & Installation ⚙️

1. **Clone the repository**:
   ```bash
   git clone https://github.com/leokook/rag-gemini-chatbot.git
   cd google-cloud-cert-bot

2. **Set up virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt

4. **Configure Google Cloud**
   
   Create a service account with:

     - BigQuery Data Owner role

     - Vertex AI User role

  Download the JSON key file
  
5. **Set up environment variables**:
    ```bash
    PROJECT=your-gcp-project-id
    REGION=us-central1  # or your preferred region
    DATASET=your_dataset_name
    TABLE=your_table_name
    GOOGLE_APPLICATION_CREDENTIALS=path/to/service-account-key.json

Running the Application 🚀

1. **Initialize the knowledge base (first time only):**
   ```bash
   python knowledge_base.py
    ```
   This loads the PDFs and creates vector embeddings (may take several minutes)
   
2. **Launch the chatbot**:
    ```bash
    streamlit run str.py

3. **Access the chatbot** :
Open your browser to http://localhost:8501


**Google Cloud Configuration** ☁️

*Ensure you have:

-Enabled these APIs:
  * Vertex AI API
  * BigQuery API
  * Cloud Resource Manager API
  
-Set appropriate quotas for:
  * Vertex AI Text Embedding model
  * BigQuery storage

- Cost considerations:
  * BigQuery storage costs apply
  * Vertex AI embedding and generation costs apply

**Project Structure 📂**
```text
google-cloud-cert-bot/
├── knowledge_base.py      # PDF loading and vector store initialization
├── ai.py                  # Core AI functionality with Gemini
├── str.py                 # Streamlit web interface
├── search.py              # Debugging tool for similarity search
├── requirements.txt       # Python dependencies
└── .env                   # Environment variables (not versioned)
```
 

**Customization** 🛠: 
  * - Add more certifications:
  *  - Edit the urls list in knowledge_base.py

  * Modify the prompt:
    - Edit the template in ai.py

 * Change model:
    - Switch between Gemini models in ai.py

**License 📄**
This project is licensed under the MIT License - see the LICENSE file for details.
