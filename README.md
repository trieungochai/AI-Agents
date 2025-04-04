## A. Accessing OpenAI large language models
### A.1 Accessing OpenAI accounts and keys
1. Go to https://openai.com and log in, or register for an account and log in. If this is your first time creating an account, you’ll likely be given free credit in some amount. If you already have an account, you must register a payment method and type. It’s generally better to purchase a number of credits at a time. This will allow you to manage the costs better and avoid overruns.

2. After logging in to the platform, select ChatGPT or the API. Choose the API.
![Selecting the API section of the OpenAI platform](/assets/A.1.png)

3. Open the left menu, and select the API Keys option
![select the API Keys option](/assets/A.2.png)

4. Click the Create button to create a new key, enter a name for the key, and click the Create Secret Key button
![Create the secret API key](/assets/A.3.png)

5. Copy and paste the key to a notepad or another area for safekeeping using the Copy button. Keep this key secret, and ensure it remains only on your development machine.
![Copying and pasting the key to a well-known safe location](/assets/A.4.png)

After generating a key, you can continue to use it within an `.env` configuration file or through other means of registering an OpenAI key. Other services, such as Azure OpenAI, will require the configuration of a model deployment and a base URL.

---
### A.2 Azure OpenAI Studio, keys, and deployments
Through its ongoing relationship with OpenAI, Microsoft hosts the same models at the same price within Azure OpenAI Studio. Occasionally, Azure may be a model version behind, but Microsoft generally keeps current with the latest OpenAI models.

These guidelines will be more general because there are several ways to access Azure and methods of creating accounts and accessing the studio (for specific instructions, refer to Microsoft documentation):
1. Log in to your Azure portal account subscription. 
2. Create a new Azure OpenAI Studio resource in a region that makes sense to you. At the time of writing, not all regions provided access to all models. You may need to check which models are available for your region first. This will also be specific to your account and usage. 

Within Azure OpenAI, models are exposed through a resource allocation called a deployment. Deployments wrap a model, such as GPT-4, and provide access to the resource.

![Deploying a model through an Azure OpenAI Studio deployment](/assets/A.5.png)

3.  Click the Create New Deployment button to create a new deployment, and then select the model you want to deploy. 
4.  After the model is wrapped in a deployment, you must access the parent Azure OpenAI resource. From there, you can access the key, end point, or base URL needed to configure your connection.

![Getting access to the keys and base URL used to access the service](/assets/A.6.png)

The three critical differences to remember when connecting to a resource such as Azure OpenAI Studio or another LLM using the OpenAI tooling are listed here:
- The api key to access the model 
- The base url or endpoint where the model is located 
- The name of the model or deployment name

---
## B. Python development environment
### B.1 Installing Python
Python is provided through different versions and deployments. This guide relies on the standard Python installation, version 3.10. Anaconda is another deployment of Python that is very popular and could be used. However, all the material in this guide has been run and tested with a Python 3.10 virtual environment:
1. Go to www.python.org/downloads/. 
2. Locate and download the latest release of Python 3.10 for your operating system. 
3. Install the release on your machine using the instructions for your operating system. 
4. To confirm your installation, open a terminal, and execute the following command: 
    ```
    python –-version
    ```
    The version should be 3.10, but if it isn’t, don't worry. You may have multiple Python versions installed.

### B.2 Installing VS Code Python extensions
Thousands of extensions for VS Code can provide an excellent Python coding environment. The recommended ones are only the start of what you can explore independently. Beware, though, that not all extensions are created equally. When installing new extensions, look at the number of installs and ratings. Extensions with fewer than four stars are generally to be avoided.

Install the following list of extensions: 
- Python, for environment and language support 
- Python Extension Pack, for covering other extensions 
- Python Environment Manager, for managing environments 
- Python Indent, for code formatting 
- Flake8, for code formatting/linting
- Prompt Flow, for testing LLM prompts
- Semantic Kernel Tools, for working with the Semantic Kernel framework 
- Docker, for managing Docker containers 
- Dev Containers, for running development environments with containers

You’ll only need to install the extensions for each VS Code environment you’re running. Typically, this will mean installing for just your operating system installation of VS Code. However, if you run VS Code in containers, you must install extensions for each container you’re running.

### B.3 Creating a new Python environment with VS Code
When developing Python projects, you often want to create isolated virtual environments. This will help in managing multiple package dependencies across various tasks and tools. In this guide, it’s recommended that a new virtual environment be created for each new chapter. VS Code can help you create and manage multiple Python environments quickly and efficiently via the following steps:
1. Press `Ctrl-Shift-P (Cmd-Shift-P)` to open the command panel, and select `Python: Create Environment`.
![The steps to set up the virtual environment for a chapter](/assets/B.2.png)
2. Select the environment type, either Venv or Conda. This book demonstrates Venv but Conda should also work. 
3. Select the Python installation. The code in this book has been run with Python 3.10 at a minimum. The agent tools and frameworks featured in this book are cutting edge, so they should support later versions of Python. 
4. Check that the `requirements.txt` file is selected. This will install all the requirements for the current source.

### B.4 Using VS Code Dev Containers (Docker)
When working with advanced agents and agents that can generate and execute code, running them in isolated containers is generally recommended. Container isolation prevents operating system disruption or corruption and provides a base for deploying agents.

Getting familiar with containers and platforms such as Docker can be an extensive undertaking to grasp everything. Fortunately, it takes very little knowledge to start using containers, and VS Code extensions make this even more accessible.

You’ll first need to install a container toolset. Follow these instructions to install Docker and get started working with containers:
1. Go to the Docker Desktop download page at `www.docker.com/products/docker-desktop`.
2. Download and install Docker for your operating system. Follow any other instructions as requested.
3. Launch the Docker desktop application. Completing this step will confirm you have Docker installed and working as expected. 
4. Open VS Code, and confirm that the Docker extensions listed in section 1.4 are installed.

With Docker and VS Code configured, you can move on to using Dev Containers by following these steps:
1. Open a new instance of VS Code.
2. Select to open a remote window.

    ![Opening a remote window to a container in VS Code](/assets/B.3.png)

3.  Select Open Folder in Container to start a container from a folder, or select New Dev Container to start without a folder. 

After the container is launched, your VS Code environment will be connected. This allows you to develop code on the container without worrying about dependencies not working.
