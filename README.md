# Operationalizing Machine Learning Pipeline

## Summary
This project is a part of the Udacity Azure ML Nanodegree. The Machine Learning project aims to predict if a client will subscribe to a term deposit of a Portuguese banking institution. [Bankmarketing Datset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv) was used to train the models. The models were trained using AutoML and best Machine Learning model was deployed as an webservice to Azure Container Instance. Finally the process was automated by crearing and deploying a pipeline.



## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model". 

## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screenshots required to demonstrate key steps. 

###Step1:Automated Machine Learning Experiment
To train models through AutoML i followed following steps
  * Firstly, I registered the dataset into the Azure ML Studio from the URI. The screenshot below shows the registered dataset.
      ![Dataset registered](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/sayed_dataset_registered.PNG "Dataset registered")

  * Secondly, I created compute cluster. The configuration of the compute cluster can be seen from the screenshot below.
      ![Dataset registered](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/sayed_cluster.png "Dataset registered")

  * Thridly, I trained a number of model with AutoML. The screenshot below shows successful completion of the AutoMl Experiment.
      ![Dataset registered](https://github.com/sayed6201/operationalizing_machine_learning/blob/master/screenshots/automl_completed.png "Dataset registered")



## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
