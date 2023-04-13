# Student Performance - Machine Learning End to End Project

- To create vertual environment with conda
--- 
    conda create -p envname python==3.8 -y
---

- Activate the vertual environment with conda
---
    conda activate envname/
---

- Create git repo , and after that clone this repository to vscode
---
    git init
---

- Create README.md file in vs code and add this file to the repository
---
    git add README.md
---

- To commit any file to repository
---
    git commit -m "message"
---

- To see the git satus
---
    git status
---

- To check the branch- main
---
    git branch -M main
---

- To sink with repository add th file to main branch
---
    git remote add origin https://github.com/dinesh4444/StudPerformance.git
---

- If you are doing for first time that time you have to set git global config
---
    git config --global user.name "your user name"
    git config --global user.email "your email address"
---

- To push data from vscode to git repository
---
    git push -u origin main
---

- To pull data from git repository
---
    git pull 
---
--------------------------------------------------------------------------------------

Create setup.py file which store the meta data of your project
   
    from setuptools import find_packages, setup

    setup(
        name="Student Performance MLproject",
        version='0.0.1',
        author='author name',
        author_email='your email address',
        packages=find_packages(),
        install_requires=get_requirements('requirements.txt'),
        
    )

---------------------------------------------------------------------------------------
- After that you have to create source files which containes init, logger, exception, utils
  files for next operations.
* Logger.py

    import sys
    from src.logger import logging

    def error_message_detail(error,error_detail:sys):
        _,_,exc_tb=error_detail.exc_info()
        file_name=exc_tb.tb_frame.f_code.co_filename
        error_message="Error occured in python script name [{0}] line number [{1}] error message[{2}]".format(
        file_name,exc_tb.tb_lineno,str(error))
        return error_message

    class CustomException(Exception):
        def __init__(self,error_message,error_detail:sys):
            super().__init__(error_message)
            self.error_message=error_message_detail(error_message,error_detail=error_detail)
        
        def __str__(self):
            return self.error_message

----------------------------------------------------------------------------------------

* Exception.py

    import sys
    from src.logger import logging

    def error_message_detail(error,error_detail:sys):
        _,_,exc_tb=error_detail.exc_info()
        file_name=exc_tb.tb_frame.f_code.co_filename
        error_message="Error occured in python script name [{0}] line number [{1}] error message[{2}]".format(
        file_name,exc_tb.tb_lineno,str(error))

        return error_message


    class CustomException(Exception):
        def __init__(self,error_message,error_detail:sys):
            super().__init__(error_message)
            self.error_message=error_message_detail(error_message,error_detail=error_detail)
        
        def __str__(self):
            return self.error_message

-------------------------------------------------------------------------------------------

* Inside the source folder create components folder is required to reading data from specific set i.e means data ingestion. After ingesting data , next step is transform the data, and model trainer.
#### Data ingestion: 
This component is responsible for collecting and importing data from various sources, such as databases, APIs, or files, into the machine learning project. It may involve data extraction, data cleaning, and data validation to ensure that the data is in a suitable format for further processing.

#### Data transformation: 
Once the data is ingested, the data transformation component processes the data to prepare it for model training. This may involve tasks such as data normalization, feature engineering, and data splitting into training, validation, and testing sets. Data transformation is crucial to ensure that the data is in a format that can be easily fed into the machine learning algorithm.

#### Model trainer Python file: 
This component is responsible for developing and training the machine learning model. It typically contains the implementation of the machine learning algorithm, including setting up the model architecture, compiling the model, and fitting it to the training data. The model trainer Python file also includes hyperparameter tuning, model evaluation, and model selection to optimize the performance of the machine learning model.

These three components work together in an end-to-end machine learning project to ensure that data is ingested, transformed, and used to train a machine learning model. The data ingestion component collects data from various sources, the data transformation component prepares the data for training, and the model trainer Python file implements the machine learning algorithm to train the model. The trained model can then be used for making predictions on new data in real-world scenarios.

----------------------------------------------------------------------------------------
* The "pipeline" folder within the source directory of an end-to-end machine learning project typically contains two main components: a training pipeline and a prediction pipeline, along with an "init.py" Python file.

#### Training pipeline: 
The training pipeline is responsible for orchestrating the various steps involved in training a machine learning model. It typically includes the data ingestion and data transformation components mentioned earlier, along with additional steps such as feature selection, model training, model evaluation, and model serialization. The training pipeline ensures that data is processed and used to train the model in a systematic and organized manner.

#### Prediction pipeline: 
The prediction pipeline handles the deployment and use of the trained machine learning model in real-world scenarios. It typically involves loading the serialized model, processing new data for prediction, and using the trained model to make predictions. The prediction pipeline ensures that the trained model is effectively utilized to make accurate predictions on new data.

#### __init__.py file: 
The __init__.py Python file is typically used as an entry point for the pipelines and serves as a central location for initializing and configuring various components of the end-to-end machine learning project. It may contain import statements, configuration settings, and initialization code for setting up the training and prediction pipelines.

These pipelines and the __init__.py file work together to create a complete end-to-end machine learning project. The training pipeline orchestrates the training process, while the prediction pipeline handles the deployment and use of the trained model. The "init.py" file serves as a central configuration and initialization point for the entire project. This modular and organized approach allows for efficient development, training, and deployment of machine learning models in real-world applications.
----------------------------------------------------------------------------------------


