# Operationalizing Machine Learning Pipeline

## Summary
This project is a part of the Udacity Azure ML Nanodegree. The Machine Learning project aims to predict if a client will subscribe to a term deposit of a Portuguese banking institution. [Bankmarketing Datset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv) was used to train the models. The models were trained using AutoML and best Machine Learning model was deployed as an webservice to Azure Container Instance. Finally the process was automated by crearing and deploying a pipeline.


## Architectural Diagram

![diagram.PNG](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/diagram.PNG "Architectural Diagram")

The models can be trained using 2 mathods oe ways, an Automated and non Automated ways. In the non automated (method 1) the model is trained using AutoML and then deployed. It does not automat the workflows. Whereas in the second method model is trained via a pipeline. Pipeline is an intedepdently executable workdlow of a complete Machine Learning task which enables external services to interact with it so that it can do work more efficiently. In this project model was trained using both methods. Best model was deployed as a webservice which allowed endpoints to intereact with it and get reponse. Then a pipeline was also created and pipeline enabled the exernal or enternal services to interact with it via HTTP API and trian the model.


## Key Steps
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

      ![application insight enabled](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/application_insight_enabled2.png "application insight monitoring")


### Step 4: Swagger Documentation
Swagger documentation is loaded in the localhost using swagger.json from the deployed model.
      ![Swagger](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/swagger.png "Swagger")
      ![Swagger](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/swagger2.png "Swagger")


### Step 5: Consuming Model Endpoints

  * Firstly, I edited the endpoint.py script with scoring_uri and key from the deployed model. The script sends HTTP request to the deployed model. The screenshot below shows endpoint.py script
      ![Endpoint py](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/endpoint_py.png "Editing endpoint.py")

  * After executing the endpoint.py script the model sends follwing resoins. 
      ![Response from the deployed model](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/endpoint_py2.png "Compute Cluster Configurationd")

  * Then i benchmarked the endpoint with Apache benchmark. 
      ![benchmarking the endpoint](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/benchmark.png "benchmarking the endpoint")
      
      
### Step 6: Create, Publish and Consume a Pipeline
To automate the workflow we need to create and publish pipeline. Published pipelines allow external services to interact with them so that they can do work more efficiently.

  * The following image shows successful completion of pipeline creation
      ![Pipeline created](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/pipeline_creation.PNG "Pipeline created")
      ![Pipeline created](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/pipeline_creation2.PNG "Pipeline created")

  * Finally the creted pipeline was published.
      ![Pipeline published](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/pipeline_published.png "Pipeline published")
      

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
