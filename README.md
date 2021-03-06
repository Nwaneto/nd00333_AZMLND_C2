# Udacity Nanodegree Project 2: MLOps in Azure

### Summary


The primary object of this venture is to foresee if a customer will buy in to a term store item identified with direct advertising efforts of a Portuguese financial foundation by making a model and sending it into creation utilizing Azure ML.

Dataset: https://www.kaggle.com/henriqueyamahata/bank-marketing 

Where we apply MLOps rule by beginning with the validating to Azure Machine Learning administrations, at that point the production of an Automated ML explore, the organization of the best model, after that we empower the logging to audit significant log data, at that point we devour the model endpoint lastly we make and distribute the pipeline to computerize this past advance.

![projectdiagrame](Main-step-project.png "projectdiagrame")

## Architectural Diagram

![architector](architector.png "architecture")

## Key Steps

**Step 1: Authentication**  *used the provided Udacity Lab*

**Step 2: Create the Automated ML Experiment**

 1. Registration of the dataset into Azure ML Studio:
 
*Figure 1: Datasets/ Bank-marketing*
![Bank-Marketing-Dataset](Bank-Marketing-Dataset.png "Bank Marketing Dataset")

 2. Create the compute cluster using Standard_DS3_V2 as VM Size:

 3. We then configure and run the AutoML Part:

 4. Now retrieve the Best Model:
 
*Figure 2: Experiments / auto-ml-exp / Run 1 (completed)*
![Best-Model](best-model.PNG "Best-Model")

**Step 3: Deploy the Best Model**

 1. We start by deploying the best Model from the previous Auto ML experiment using ACI.

 2. And finally create the endpoints 
 
**Step 4: Enable Application Insights to retrieve logs**

 1. Where we start by provided logs.py by adding the name of the deployed model. 
 
*Figure 3: logs.py(Modification)*
 ![Enable-application-insight](application-insight-enabled.PNG "Enable-application-insight")
 
  2. we then execute the logs.py file 
  
*Figure 4: logs.py(Execution)*
  ![log-application-insight](logspy-running.PNG "log-application-insight")
  
  3. To finally access to application insight  from the endpoints 
 
 
 **Step 5: Consume the deployed model using Swagger**
 
  1. Where we start by downloading the swagger.json file associated with the deployed model
  
 *Figure 5: Swagger.json*
   ![Swagger-json](my-model-running-on-swagger.PNG "Swagger-json")
   
  2. We next execute the provided swagger.sh 
  
 *Figure 6: Swagger default page*
   ![swagger-default-page](swagger-running-on-localhost.PNG "swagger-default-page.PNG")
   
  3. To finally display the API Documentation of the model 
  
 *Figure 7: Swagger documentation associated to the model endpoints*
   ![swagger-endpoints](swagger-payload.PNG "swagger-endpoints")
   
 **Step 6: Consume the Model Endpoints**
 
  1. Where we start by modifying a provided endpoints.py by adding the scoring_uri 
     
  2. To finally run the endpoint.py to interact with the trained model
  
 *Figure 8: Interaction with the model using endpoint.py*
   ![endpoints-result](endpointpy-runs.PNG "endpoints-result")
   
   **Step 7: Create, Publish and Consume a Pipeline to automate all these previous steps in one python SDK**

  1. Use aml-pipelines-with-automated-machine-learning-step.ipynb 
  
  2. Now download the config.json file and place it in the working directory
  
  3. And finally Run the different cells.
 
  *Figure 9: Pipeline creation (jupyter Notebook)*
  ![pipeline-completed](pipeline-completed.PNG "pipeline-completed")
  
  *Figure 10: Pipeline creation (azure ml studio)*
  ![pipeline-creation](pipeline-created.PNG "pipeline-creation")
  
  *Figure 11: Pipeline run overview (azure ml studio)*
  ![pipeline-rest-endpoint](scheduled-run.PNG "pipeline-rest-endpoint")
  
   *Figure 12: Run details widget showing runs(jupyter Notebook)*
  ![pipeline-EXP](run-details-widget-showing-runs.PNG "pipeline-EXP")
  
    . Create the Rest endpoint associated with the pipeline
    
   *Figure 13: Published pipeline overview*
 ![pipeline-published](active-publishes-pipeline.PNG " pipeline-publishe")
  
  

## Screen Recording Video: https://youtu.be/8SVF-T54hrE

I have no future proposals yet.
