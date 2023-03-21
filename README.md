# End to end ML Project Template

## 5 Steps:
1. Data Ingestion
2. Data Trnsformation
3. Model Trainer
4. Model Evaluation
5. Model Deployment

### To create a new environment
conda create -p ./venv python=3.8 -y # -p option specifies the path where the new environment should be created


### setup.py and requirements.txt file
- This template can be used with any project, follow below steps
- Create .gitignore in Github: A .gitignore file specifies intentionally untracked files that Git should ignore, create this directly from github repo (use python template)
- Create a setup.py file in root directory: setup.py is a Python script used for distributing and installing packages. It is typically included in the root directory of a Python project and is used to describe metadata about the project, such as the package name, version, author, and dependencies
- Create a src directory and create __init__.py file in it: When a directory is defined as a package in Python, it must contain an __init__.py file, even if the file is empty. The purpose of the __init__.py file is to signal to Python that this directory should be considered a package and to specify any initialization code that should be executed when the package is imported.
- Create requirements.txt: a file that is commonly used to list the dependencies (i.e., external packages or libraries) required by a Python project to run; def get_requirements() in setup.py will read requirements
(1) pip install -r requirements.txt
(2) also include "-e ." in one of the lines within requirements.txt, to auto trigger setup.py file
- Now when we run pip install -r requirements.txt, it will build the package and create mlproject.egg-info which contains the project’s metadata, now we can deploy it in pypi as a package

### Directories:
- Create src/components: where all the project code will reside; data_ingestion.py, data_transforamtion.py, model_trainer.py
- Create src/pipeline: train_pipeline.py and predict_pipeline.py file is created
- Within src 3 important files will be created: logger.py, exception.py, utils.py (this will hold common functionality, e.g. mongo db client to read dataset from mongo db, save model to cloud etc.) 
- Now write exception and logger related code