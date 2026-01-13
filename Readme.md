# 🎬 Content-Based Movie Recommendation Platform (TF-IDF & Similarity Search)
![Python](https://img.shields.io/badge/Python-3.9+-blue)
![Status](https://img.shields.io/badge/Status-Stable-green)

A production-oriented movie recommendation system that delivers content-based suggestions using TF-IDF vectorization and cosine similarity.  
The project demonstrates end-to-end machine learning inference, backend logic separation, and an interactive frontend built for real-world usage.


## 📌 Project Overview

Modern content platforms rely heavily on intelligent recommendation systems to improve user engagement and content discovery.  
This project implements a **content-based movie recommendation platform** that suggests similar movies based on textual metadata rather than user behavior.

The system is designed to:
- Analyze movie content representations
- Identify semantic similarity between items
- Generate meaningful recommendations in real time
- Serve results through an interactive and user-friendly interface

Unlike collaborative filtering approaches, this platform does **not depend on user history or ratings**, making it suitable for cold-start scenarios and standalone recommendation use cases.

The overall solution focuses on:
- Deterministic and explainable recommendations
- Efficient inference using precomputed representations
- Clear separation between frontend interaction and backend logic
- Practical deployment readiness


## ⚙️ Key System Capabilities

- **Content-Based Recommendations**  
  Generates movie suggestions by analyzing semantic similarity between movie descriptions and metadata, ensuring relevance without relying on user behavior or ratings.

- **Cold-Start Friendly Design**  
  Operates independently of user history, making the system effective even for first-time users or newly added content.

- **Real-Time Recommendation Inference**  
  Delivers fast and consistent recommendations using precomputed content representations optimized for inference-time performance.

- **Interactive User Interface**  
  Provides an intuitive frontend experience that allows users to search for movies, explore related content, and view recommendations seamlessly.

- **Backend Logic Isolation**  
  Separates recommendation logic from the presentation layer, enabling easier maintenance, testing, and potential future extensions.

- **Deployment-Ready Architecture**  
  Structured to support local execution as well as cloud-based deployment with minimal configuration changes.


  ## 🏗 System Architecture Overview

The platform follows a modular and layered architecture designed to clearly separate user interaction, recommendation logic, and data representation. Each layer is implemented using technologies chosen for reliability, simplicity, and production suitability.

At a high level, the system consists of the following components:

- **Frontend Layer (Streamlit)**  
  A lightweight interactive interface responsible for capturing user input, initiating recommendation requests, and presenting results in a clear and user-friendly manner.

- **Recommendation Engine (Python / Scikit-learn)**  
  A backend module that performs content similarity evaluation using precomputed textual representations. The engine focuses on deterministic, explainable inference rather than online learning or user behavior tracking.

- **Data Artifacts Layer (Serialized Models & Data)**  
  Preprocessed and serialized data structures used to store movie metadata and content representations, optimized for fast loading and efficient inference at runtime.

- **Integration & Utility Services**  
  Supporting components responsible for configuration management, environment setup, and controlled interaction with external services when required.

This architectural separation ensures maintainability, scalability of individual components, and a clean boundary between presentation, logic, and data.


## 📁 Project Structure

The repository is organized to maintain a clear separation between application layers, data artifacts, and configuration files.

├── app.py                 # Frontend application (user interaction & presentation)

├── main.py                # Core recommendation logic and backend operations

├── requirements.txt       # Project dependencies

├── runtime.txt            # Runtime configuration for deployment environments

├── .python-version        # Python version consistency

├── .gitignore             # Git ignore rules

│

├── df.pkl                 # Serialized movie metadata

├── tfidf.pkl              # Serialized text vectorization model

├── tfidf_matrix.pkl       # Precomputed content representation matrix

├── indices.pkl            # Index mapping for fast lookup

│

└── README.md              # Project documentation


## 🧪 Setup & Local Execution

### Prerequisites
- Python 3.9 or higher
- Virtual environment support
- Git

### Local Setup

Clone the repository and navigate to the project directory:

```bash
git clone <repository-url>
cd <repository-directory>
```

Create and activate a virtual environment:
```bash
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate
```

Install project dependencies:
```bash
pip install -r requirements.txt
```

### Running the Application
Start the frontend application locally:
```bash
streamlit run app.py
```
Once running, the application will be accessible through the local browser interface provided by Streamlit.


## 🚀 Deployment Notes

The application is structured to support both local execution and cloud-based deployment with minimal configuration changes.

Key deployment considerations:
- Dependencies are fully declared and version-pinned to ensure environment consistency.
- Precomputed data artifacts are loaded at runtime to minimize startup latency during inference.
- The frontend and recommendation logic are decoupled, allowing flexibility in hosting strategies.
- Runtime configuration files are included to support managed deployment environments.

The project has been tested in a managed cloud environment and is suitable for lightweight production deployments, demos, and proof-of-concept use cases.


## ⚖️ Design Decisions & Limitations

### Design Decisions

- **Content-Based Recommendation Approach**  
  The system intentionally uses content-based similarity to ensure deterministic and explainable recommendations without relying on user interaction data.

- **Precomputed Representations**  
  Content representations are prepared in advance and loaded at runtime to optimize inference speed and reduce computational overhead during user requests.

- **Clear Layer Separation**  
  Frontend interaction, recommendation logic, and data artifacts are separated to improve maintainability and allow independent evolution of each component.

- **Inference-Only Architecture**  
  The platform is designed strictly for inference, avoiding online training or dynamic model updates to ensure stability and predictable behavior.

### Limitations

- **No Personalized User Modeling**  
  Recommendations are generated based solely on content similarity and do not adapt to individual user preferences or behavior over time.

- **Static Data Scope**  
  The system operates on a predefined dataset and does not currently support dynamic ingestion of new content during runtime.

- **Single-Strategy Recommendation**  
  Hybrid or collaborative filtering techniques are intentionally excluded to maintain system simplicity and explainability.

These constraints reflect deliberate architectural choices rather than technical shortcomings and align with the project’s scope and goals.


----

## 🛡 Ownership & Usage Disclaimer

This repository represents original work developed as part of a personal engineering project.  
It is intended for educational, demonstrational, and evaluation purposes only.

You are welcome to:
- Review the code and architecture
- Learn from the system design and documentation
- Run the project locally for personal understanding

You are **not permitted** to:
- Reproduce this project in full or in part for commercial purposes
- Submit this work as your own in academic or professional settings
- Deploy or redistribute the system without explicit permission

If you are interested in extending, adapting, or using this project beyond personal evaluation, please contact the author to discuss appropriate usage.

This disclaimer exists to protect the intellectual effort behind the project while encouraging responsible learning and collaboration.

----

## 🔐 Security & Privacy Notes

This project has been designed with security awareness and data responsibility in mind.

- **No Personal User Data**  
  The system does not collect, store, or process any personal or sensitive user information. All recommendations are generated solely from predefined content metadata.

- **No Authentication or Session Handling**  
  The application does not implement user accounts, authentication flows, or session tracking, reducing the overall security surface.

- **Environment Configuration Safety**  
  Environment-specific settings and sensitive configuration values are intentionally excluded from version control and managed locally when required.

- **Read-Only Data Usage**  
  Precomputed data artifacts are loaded in a read-only manner during runtime, preventing unintended modification or persistence of state.

- **Minimal External Exposure**  
  The system avoids unnecessary external integrations and limits runtime operations to essential application functionality.

These measures align with the scope of the project and ensure that the application remains safe, transparent, and suitable for demonstration and evaluation purposes.

----

## 🤝 Contribution Guidelines

Contributions are welcome in the form of thoughtful suggestions, improvements, and constructive feedback.  
This project is maintained with a focus on clarity, architectural consistency, and defined scope.

### Before Contributing
- Review the project documentation to understand design goals and constraints.
- Ensure proposed changes align with the existing system architecture and intent.
- Avoid introducing additional complexity or dependencies without clear justification.

### Contribution Scope
Appropriate contributions may include:
- Documentation improvements or clarifications
- Code quality refinements that preserve existing behavior
- Performance or maintainability enhancements within the current design

Out-of-scope contributions include:
- Major architectural changes without prior discussion
- Introduction of unrelated features or frameworks
- Modifications that alter the core recommendation strategy

### Process
- Open an issue to discuss proposed changes before submitting a pull request.
- Clearly describe the motivation and impact of the contribution.
- Ensure all changes are well-documented and tested where applicable.

All contributions are reviewed with respect for the project’s original intent and scope.


