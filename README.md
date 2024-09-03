# GraphRAG Pipeline
This README provides step-by-step instructions for setting up and running the GraphRAG pipeline.

## Get access to required account
Before proceeding, you must have account on EIT and Sutra. If you need to create a new account, please contact one of the following:
* Lavinia Xu: lavinia.x@wustl.edu
* Jiarui Feng: feng.jiarui@wustl.edu

## Connect to the server
Once your accounts are set up, connect to the server using the following command in your Terminal:
```
ssh wustl.key@ssh.seas.wustl.edu
```
Please replace `wustl.key` with your specific username.

## Install Python environment
To install the Python environment required for GraphRAG, follow these steps:
1. Download and install Miniconda:
   ```
   wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
   bash Miniconda3-latest-Linux-x86_64.sh
   ```
   For more detailed information, please refer to [the Miniconda documentation](https://docs.anaconda.com/miniconda/).
2. Create a new conda environment:

   To avoid altering the base environment, create and activate a new conda environment using the following command:
   ```
   conda create --name <environment_name> python==3.11
   conda activate <environment_name>
   ```
   Please replace `<environment_name>` with your desired name for the environment.

## Install GraphRAG
```
pip install graphrag
```
To verify that GraphRAG is correctly installed, run:
```
pip show graphrag
```
If the installation is successful, you should see an output similar (potentially with different versions):
<img width="1148" alt="Screenshot 2024-08-30 at 10 52 54 AM" src="https://github.com/user-attachments/assets/339a4dea-0ee2-43e7-932c-79486c3b4b74">

## Navigate to the project folder
Change to the appropriate project directory:
```
cd /project/tantra/xtxxxxxtx
```

## Run the query engine
Here are examples of how to use the GraphRAG query engine:
* **Global Search**: To ask a high-level question, run:
  ```
  python -m graphrag.query \
  --root ./rag0809 \
  --method global \
  "How is amyloid beta removed from the brain?"
  ```
* **Local Search**: To ask a more specific question about a particular step, run:
  ```
  python -m graphrag.query \
  --root ./rag0809 \
  --method local \
  "How do amyloid beta circadian patterns change with respect to age and amyloid pathology?"
  ```
**Note**: The input files within the **`rag0809`** directory (or any new directories) will be regularly updated. Please check your email or this page for updates.
