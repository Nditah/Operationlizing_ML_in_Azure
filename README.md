# :star: Operationalizing The Machine Learning Model In Azure

This project is part of the Udacity Azure ML nanodegree.In this project,we use both Azure ML studio and pyhton SDK to build Automated ML experiment to deploy the best model by enabling authentication.Then, we enable the Application Insights to review importatnt information about the service when consuming the model.And, finally we will create, publish and interact with a pipeline.The main objective of this project is to build a machine learning model using Azure Container Services.We are provided with the banking dataset.
The main steps to be followed to perform project are as follows :-

1) Authentication
2) Automated ML Experiment
3) Deploy the best model
4) Enable logging
5) Swagger Documentation
6) Consume model endpoints
7) Create and publish a pipeline
9) Documentation

# :star: Architectural Diagram

![diagram](screenshots/image.png)

:pushpin: **Authentication** :- Authentication is crucial for the continuous flow of operations, continuous Integration and delivery system(CI/CD) rely on uninterrupted flows. If authentication is not set properly it requires human interactions and thus the flow is interrupted. Thus, its good to use authentication with automation because in ideal scenario the system doesn't stop waiting for a user to input a password.

Authentication types :-
 1) Key based
 2) Token based
 3) Interactive
 
:pushpin: **AutoML model** :- AutoMl is the process of automating the time consuming iterative tasks of machine learning models.AutoML iterates the each and every machine learning algorithms for the particular datasets which we assigned in azure and gives us the results of each algorithm.With automated machinelearning, you'll accelerate the time it takes to get production ready ML models with great ease and efficency.During training period,AutoML creates a several pipelines in parallel which tries different algorithms,parameters,feature selections and also with different metrices and produces a model with a trainig score.
 
:pushpin: **Deploy the best model** :-Deployment is about delivering a trained model into production so that it can be consumed by others.After deploying the model we need to know whether a model is working as excepted or no.User can initate an input request, usually via HTTP POST request.Here the model is deployed in ACI Azure container instance where ACI offers the fastest and simplest way to run a conatiner and also authentication is enabled to prevent unauthorized access.
 
:pushpin: **Enable logging** :-Logging is nothing but the informational output produced by the software usually in the form of text.Application insights is very useful tool to detect anomalies, visualize performance.It can be enabled before or after a deployment of the model.
 
 :pushpin: **Consume model endpoint** :-Here the endpoints allow other services to interact with deployed models.
             There are some interesting details we need to be aware of when trying to use HTTP and you will go through each of these:-
             
   1) Swagger
                    
   2) Consuming deployed services 
                    
   3) Benchmarking
                    
 * Swagger : A tool that eases the documentation efforts of HTTP API's.
  
 * Benchmarking : Being able to create a baseline of acceptable performance so that it can be compared day-to-day behavior.
  
 :pushpin: **Create and publish a pipeline** :- Automation is the core pillar of Deveops applicable to machine learning operations.A good features of azure is pipelines and there are closely related to automation.Some key factors covered about pipelines are:-
 
 1) Creating a pipeline
 
 2) Publishing a pipeline
 
 3) Interacting with a pipeline via HTTP API endpoint
 
 **Create a pipeline** :- This is the most common python SDK class you will see when dealing with the pipelines.Aside from accepting a workspace and allowing multiple steps to bepassed in,it uses a description that is useful to identify it later.
 
 **Publish a pipeline** :- Publishing a pipeline is the process of making a pipeline publicaly available.We can publish pipelines in azure machine learning studio,but we can also do it with python SDK.When pipeline is published, a public HTTP endpoint becomes available, allowing other services, including external ones to interact with an azure pipelines.
 
 :pushpin: **Documentation** :- I have documented the process by creating the screencast of this project as well as this readme.md file describes the complete process of the second project. 
  


# :star: Key Steps

1) **Authentication** 

![Auth](screenshots/authentication.png)

2) **Automated ML Experiment** :- First we need to register the dataset,run the notebook to build AutoML model for BankMarketing Dataset,Here VotingEnsemble is the best model.

![dataset](screenshots/dataset.png)

![run](screenshots/run1.png)

![run2](screenshots/run2.png)

![run3](screenshots/run3.png)

![run11](screenshots/run11.png)

![voting](screenshots/voting.png)

3) **Deploy the best model** :- After getting a best model need to deploy the model in Azure Container Instance.

![app](screenshots/application_enable.png)

![app2](screenshots/application_enable1.png)

4) **Enable Logging** :- Download a config.json file which holdes information to understand where we need to go in which workspace we need to be associated with.Paste config.json file in the current directory.Its nice way to automate where and with whom we are interacting with.Execute LOGS.PY file,you can see in endpoint section that application insights is enabled that's nothing but true.

![applog](screenshots/application_logging.png)

![apping](screenshots/true_applicationinsights.png)

![app3](screenshots/application3.png)

5) **Swagger Documentation** :- After enabling application insights,In endpoint section click on swagger.json file,download it and paste in the swagger folder where serve.py and swagger.sh is present.If port 80 is not working then switch tp port 8000 or above 8000 which is a good choice to interact with swagger ui.Swagger serve grabs this information and it will transform it into the beautiful website.

![swag1](screenshots/Swagger_log1.png)

![swag2](screenshots/Swagger_log2.png)

![swag3](screenshots/Swagger_log3.png)

![swag11](screenshots/swagger_log4.png)

![swag4](screenshots/Swagger_2.png)

6) **Consume Model Endpoints** :-In endpoint section, In consume section we get REST endpoint and primary key copy it and again go to terminal make changes in the endpoint.py.Replace scoring_uri and key with present best deployed model REST endpoint and primary key.We get data.json file which holds information.Then execute benchmark.sh to get baseline for the model.

![end1](screenshots/endpoint1.png)

![end2](screenshots/endpoint2.png)

![data](screenshots/datajsonfile.png)



![bench](screenshots/benchmark1.png)

![bench2](screenshots/benchmark2.png)

![bench](screenshots/benchmark3.png)

7) **Create and Publish Pipeline** :- Publish pipeline means making pipeline publically available.

![pip](screenshots/pipeline1.png)

![pip3](screenshots/Pipeline_3.png)

![pip5](screenshots/Pipeline_5.png)

![pip9](screenshots/pipeline9.png)



# :star: Screen Recording

The whole project demo is implemented in the [recording](https://drive.google.com/file/d/1yCudhaKlDwIoxo_z8gYCRbqYl54R_FVB/view?usp=sharing) section.

# :star: References

:sparkles: [Microsoft_documentation](https://docs.microsoft.com/en-us/documentation/)

:sparkles: [set_up_authentication](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-setup-authentication)

:sparkles: [Application_insights](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-enable-app-insights)

:sparkles: [troubleshooting](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-troubleshoot-deployment?tabs=azcli)

:sparkles: [compute_instance](https://docs.microsoft.com/en-us/azure/machine-learning/concept-compute-instance)

:sparkles: [Swagger_home_page](https://swagger.io/tools/swagger-ui/)

:sparkles: [How_to_consume_webservice](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-consume-web-service?tabs=python)

:sparkles: [Apache_benchmark_tool](https://httpd.apache.org/docs/2.4/programs/ab.html)

:sparkles: [Machinelearning_pipelines](https://docs.microsoft.com/en-us/azure/machine-learning/concept-ml-pipelines)

:sparkles: [Create_run_ML_Pipeline](https://docs.microsoft.com/en-us/azure/machine-learning/how-to-create-machine-learning-pipelines)

:sparkles: [Pipeline_endpoint_class](https://docs.microsoft.com/en-us/python/api/azureml-pipeline-core/azureml.pipeline.core.pipeline_endpoint.pipelineendpoint?view=azure-ml-py)

