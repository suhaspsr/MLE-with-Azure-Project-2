# Operationalizing Machine Learning

## Overview
This is an overview of the second project in the udacity course MLE with Azure. In this project, we have created an azure dataset and using it we ran an AutoML job to find the best model. We deployed the model and consume its endpoints using Azure compute instance and swagger respectively. Later we publish the pipleline and use it to post the payload.

## Architectural Diagram
*Figure 1: Architectural Diagram*
![Architectural Diagram](Screenshots/Architecture.png)

## Key Steps
**1. Authentication :** 

I skipped this step as I am using the lab Udacity account.

**2. Automated ML Experiment :** 

A compute cluster was spinned off , using the bank marketing dataset
I ran an Automated ML experiment. This experiment identified VotingEnsemble to be the best 
model with a weighted AUC of 0.947. 

*Figure 2: Registered Dataset*

As can be seen in the figure, the *bankmarketing_train.csv* was successfully uploaded as a registered dataset named 
*bank-dataset*.
![Registered Dataset](Screenshots/Fig1.png)

*Figure 3: Experiment Completion*

AutoML produced VotingEnsemble as the best model under 20 mins with as AUC 0.947.

![Experiment Completion](Screenshots/Fig2.png)

*Figure 4: AutoML Models*

The figure shows all the models evaluated by the AutoML experiment and their corresponding weighted AUCs.
![Step 2 - Best Model 1](Screenshots/Fig3.png)

*Figure 5: Best AutoML Model Metrics*

The figure shows the metrics for the best model (VotingEnsemble). 
![Step 2 - Best Model 1](Screenshots/Fig4.png)

**3. Deploy the best model :** 

I deployed the best model using Azure Container Instance (ACI) with authentication enabled. 

*Figure 6: Model Deployment and Application Insights Enabled*

The figure shows the deployed model, endpoint page which has been updated to reflect that application insights are now enabled.

![Model Deployment](Screenshots/Fig5.png)

**4. Enable logging :**

I edited and ran the provided *logs.py* to enable logging. This helped monitor the deployed model and keep track of the
request frequency, latency, etc.

*Figure 7: Running Logs*
![Running Logs](Screenshots/Fig6.png)


**5. Swagger Documentation :**

I downloaded *swagger.json* and ran both *swagger.sh* and *serve.py*. 

*Figure 8: Serving Swagger Directory*
![Serving Swagger Directory](Screenshots/Fig7.png)

*Figure 9: Swagger UI*
![Swagger UI Container](Screenshots/Fig8.png)

*Figure 10: Swagger API*
![Swagger API](Screenshots/Fig14.png)

**6. Consume model endpoints :**

By modifying and running *endpoint.py*, I can post the payload to the deployed model endpoint and get results.

*Figure 11: Consume Model*

The figure shows the model is returning predictions when the updated *endpoint.py* is run.
![Consume Model](Screenshots/Fig9.png)

**7. Create and publish a pipeline :** 

I uploaded and updated the jupyter notebook provided to match the environment. 

*Figure 12: Pipeline*

The figure shows the pipeline has been submitted from the Jupyter notebook and is now running with information available in ML studio. 
![Pipeline Running](Screenshots/Fig10.png)

*Figure 13: Published Pipeline Run*

![Published Pipeline](Screenshots/Fig13.png)

*Figure 14: Pipeline Completion Notebook*

The figure shows the pipeline run has completed in the Jupyter notebook.
![Pipeline Completion Notebook](Screenshots/Fig11.png)

![Pipeline Completion](Screenshots/Fig12.png)

** Documentation

## Screen Recording of the Project
[https://youtu.be/97uhnickb0M](https://youtu.be/nJ2ul4lc84U)


