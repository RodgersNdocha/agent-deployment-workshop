# Getting Started

This guide will walk you through setting up the necessary environment for the examples in this course.

---

## Setup Environment

You only need to create one virtual environment for all the examples. Follow these steps to set it up:

1.  **Create the virtual environment** in your project's root directory.

    ```bash
    python -m venv .venv
    ```

2.  **Activate the environment** each time you open a new terminal. The command will depend on your operating system:

    * **macOS/Linux:**
        ```bash
        source .venv/bin/activate
        ```

    * **Windows CMD:**
        ```cmd
        .venv\Scripts\activate.bat
        ```

    * **Windows PowerShell:**
        ```powershell
        .venv\Scripts\Activate.ps1
        ```
## Install Google ADK

First, activate your virtual environment, then run the following command to install Google ADK:

```bash
pip install google-adk
```

---


## Setting Up API Keys

1.  Create an account on **Google Cloud**: [https://cloud.google.com/](https://cloud.google.com/)
2.  Create a **new project**.
3.  Go to the API key creation page in **Google AI Studio**: [https://aistudio.google.com/apikey](https://aistudio.google.com/apikey)
4.  Click to **Create an API key**.
5.  **Assign the key** to the project you created.
6.  Ensure your project is connected to a **billing account**.
7.  Navigate to the specific example folder you are working with.
8.  Open the `.env` file and replace the placeholder with your actual API key:

    ```env
    GOOGLE_API_KEY=your_api_key_here
    ```

Deploying to Cloud and Setting Environment Variables
Setup and Installation
First, set your essential environment variables. These are required for the ADK to interact with your Google Cloud environment correctly.
```
export GOOGLE_CLOUD_PROJECT=your-project-id
export GOOGLE_CLOUD_LOCATION=us-central1 # Or your preferred location
export GOOGLE_GENAI_USE_VERTEXAI=True
```
adk CLI Deployment
The adk deploy cloud_run command is used to deploy your agent code to Google Cloud Run.

1. Authenticate with Google Cloud
Before deploying, ensure you have authenticated your gcloud CLI and configured it with your project.
```
gcloud auth login
gcloud config set project <your-project-id>
```
2. Setup Environment Variables for Deployment
While optional, setting these environment variables can make your deployment commands cleaner and less prone to errors.

# Set your Google Cloud Project ID
```
export GOOGLE_CLOUD_PROJECT="your-gcp-project-id"
```
# Set your desired Google Cloud Location
```
export GOOGLE_CLOUD_LOCATION="us-central1" # Example location
```
# Set the path to your agent code directory
```
export AGENT_PATH="./capital_agent" # Assuming capital_agent is in the current directory
```
# Set a name for your Cloud Run service (optional)
```
export SERVICE_NAME="capital-agent-service"
```
# Set an application name (optional)
```
export APP_NAME="capital-agent-app"
```
3. Command Usage
Once your variables are set, you can use them in the deployment command.

Minimal Command
This is the simplest version of the command, using the required flags.
```
adk deploy cloud_run \
--project=$GOOGLE_CLOUD_PROJECT \
--region=$GOOGLE_CLOUD_LOCATION \
$AGENT_PATH
```
Full Command with Optional Flags
This command includes additional optional flags for more control over the deployment.
```
adk deploy cloud_run \
--project=$GOOGLE_CLOUD_PROJECT \
--region=$GOOGLE_CLOUD_LOCATION \
--service_name=$SERVICE_NAME \
--app_name=$APP_NAME \
--with_ui \
$AGENT_PATH
```
