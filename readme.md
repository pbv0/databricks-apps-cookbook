# 📖 Databricks Apps Cookbook 🍳

Ready-to-use code snippets for building interactive data applications using [Databricks Apps](https://docs.databricks.com/en/dev-tools/databricks-apps/index.html).
* **10+ recipes for common use cases** such as reading and writing to and from tables and volumes, invoking traditional ML models and GenAI, or triggering workflows.
* **Try recipes in the Cookbook app** and simply copy a code snippet to build your own.
* **Description of requirements** (permissions, resources, dependencies) for each recipe.
* Deploy to Databricks Apps or run locally.
* Snippets for both **Dash and Streamlit** are available.

![Cookbook](cookbook.png)

> [!WARNING]  
> This code sample is experimental and not intended for production use. It is a personal project provided by the contributors and not by Databricks.

## Deploy to Databricks
1. [Load this repository as a Databricks Git folder](https://docs.databricks.com/en/repos/index.html) in your Databricks workspace.
1. In your Databricks workspace, switch to **Compute** -> **Apps**.
1. Choose **Create app**.
1. Under **Choose how to start**, select **Custom** and choose **Next**.
1. Provide a name for your app and choose **Create app**.
1. Once your app compute has started, choose **Deploy**.
1. Navigate to your new Git folder and select either the `dash` or `streamlit` folder.
1. Choose **Deploy**.

> [!IMPORTANT]  
> Check the Requirements tab of each recipe to understand what [service principal permissions](https://docs.databricks.com/en/dev-tools/databricks-apps/app-development.html#configure-resources), Databricks resources, and Python packages are required to use it.

## Run locally
1. [Clone this repo](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) to your local machine and switch into the `databricks-apps-cookbook` folder:
   ```bash
   git clone https://github.com/pbv0/databricks-apps-cookbook.git
   cd databricks-apps-cookbook
   ```
1. Navigate to the sub-folder for the cookbook framework you want to run (either `dash` or `streamlit`). Create and activate a Python virtual environment in this folder [`venv`](https://docs.python.org/3/library/venv.html). We recommend using separate environments for each framework:
   ```bash
   cd streamlit
   python3 -m venv .venv
   source .venv/bin/activate
   ```
1. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```
1. Install the [Databricks CLI](https://docs.databricks.com/en/dev-tools/cli/index.html) and authenticate with your Databricks workspace using [OAuth U2M](https://docs.databricks.com/en/dev-tools/auth/oauth-u2m.html), for example:
   ```bash
   databricks auth login --host https://my-workspace.cloud.databricks.com/
   ```
1. Set required environment variables:
   ```bash
   export DATABRICKS_HOST=https://my-workspace.cloud.databricks.com/
   ```
1. Run the Cookbook app locally (make sure your virtual environment is activated).
   
   Streamlit:
   ```bash
   streamlit run app.py
   ```
   Dash:
   ```bash
   python app.py
   ```

> [!IMPORTANT]  
> Make sure you have a working network connection to your Databricks workspace. Some samples may only work when running on Databricks Apps and not locally, e.g., retrieving information from HTTP headers to identify users.

## Contributions
We welcome contributions! Submit a [pull request](https://github.com/pbv0/databricks-apps-cookbook/pulls) to add or improve recipes. Check out the roadmap below for inspiration. Raise an [issue](https://github.com/pbv0/databricks-apps-cookbook/issues) to report a bug or raise a feature request.

## Roadmap / recipes wanted
* Display coordinates from a Delta table in a map component
* Display data from a Delta table in Streamlit/Dash-native diagram components
* Gradio implementation
* Flask implementation
