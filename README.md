# Operationalizing Machine Learning Pipeline

## Summary
This project is a part of the Udacity Azure ML Nanodegree. The Machine Learning project aims to predict if a client will subscribe to a term deposit of a Portuguese banking institution. [Bankmarketing Datset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv) was used to train the models. The models were trained using AutoML and best Machine Learning model was deployed as an webservice to Azure Container Instance. Finally the process was automated by crearing and deploying a pipeline.



## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model". 

## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screenshots required to demonstrate key steps. 

### Step 1: Automated Machine Learning Experiment
To train models through AutoML i followed following steps
  * Firstly, I registered the dataset into the Azure ML Studio from the URI. The screenshot below shows the registered dataset.
      ![Dataset registered](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/sayed_dataset_registered.PNG "Dataset registered")

  * Secondly, I created compute cluster. The configuration of the compute cluster can be seen from the screenshot below.
      ![Compute Cluster Configuration](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/sayed_cluster.png "Compute Cluster Configurationd")

  * Thridly, I trained a number of model with AutoML. The screenshot below shows successful completion of the AutoMl Experiment.
      ![Automl Completed](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/automl_completed.png "Automl Completed")

    The screenshot below shows top 11 models with higest accuracy. VotingEnsamble model had the higest accuracy of all
      ![Automl Models](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/automl_models.png "Automl Models")


### Step 2: Deploying The Best Model
  * The best model was VotingEnsamble model which had accuracy of 92%. Some details of the model can be viewed in the screenshot below
      ![votingensamble model](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/votingensamble.png "Best model: votingensamble model")

  * The votingEnsamble model was then deployed using Azure Container Instance with authentication enabled.
      ![deploying best model.png](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/deploying_best_model.png "deploying best model")     


### Step 3: Enable Logging
Through Azure Application insight the logging data of deployed model can be monitored. It comes in handy in detecting any failures or anomalies

  * Firstly, i edited the logs.py file and set application insight to true and then executed the python script
      ![logs.py file](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/logs_py.png "Editing logs.py file")
       
      logs.py getting executed. 
      ![logs.py executing](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/logs_execute.png "Editing logs.py file getting executed")

  * After running the logs.py the Application insight got enabled in the Azure ML Studio.
      ![application insight enabled](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/application_insight_enabled.PNG "application insight enabled")

      ![application insight enabled](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/application insight enabled2.png "application insight monitoring")


### Step 4: Swagger Documentation
To train models through AutoML i followed following steps
  * Firstly, I registered the dataset into the Azure ML Studio from the URI. The screenshot below shows the registered dataset.
      ![Dataset registered](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/sayed_dataset_registered.PNG "Dataset registered")

  * Secondly, I created compute cluster. The configuration of the compute cluster can be seen from the screenshot below.
      ![Compute Cluster Configuration](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/sayed_cluster.png "Compute Cluster Configurationd")

  * Thridly, I trained a number of model with AutoML. The screenshot below shows successful completion of the AutoMl Experiment.
      ![Automl Completed](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/automl_completed.png "Automl Completed")

    The screenshot below shows top 11 models with higest accuracy. VotingEnsamble model had the higest accuracy of all
      ![Automl Models](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/automl_models.png "Automl Models")



## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
