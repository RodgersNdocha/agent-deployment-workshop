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

