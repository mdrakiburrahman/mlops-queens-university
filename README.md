# mlops-queens-university
Big Data and MLOps content presented at Queen's University MMAI Workshop

_This repo contains the content I presented at the Queen's University MMAI Workshop ([link](https://www.eventbrite.ca/e/understanding-mlops-with-azure-tickets-92138423505))._

# Primary components
We're going to demo the three **core** components that make up mlflow: <br>
![MLflow](https://i.imgur.com/vulSrq4.png)<br>
  
**Note**: you don't have to use all three, each feature can be used independently. <br>
  
#### Tracking
This allows us to **log all aspects of the ML process** - like _different hyperparameters_ we tried, _evaluation metrics_, as well as the code we ran - alongside other arbitrary artifacts such as _test data_. <br>

This also provides a _leaderboard-style UI_ that makes it easy to see which model performed the best.

#### Projects
These are all about **reproducibility and sharing**. They combine _GIT_, the environment/model framework, either _conda_ or _docker_ and the specification that makes the code re-runnable. 

#### Models
An abstraction that allows us to **create/export models** from any open source framework via the _Tracking_ and _Projects_ abstractions. We can also export them to a standard format that can be deployed to any number of systems. Since most deployment systems use some sort of container based solution (e.g. _AzureML_ or _Sagemaker_), models make easy deployments to these systems - or we can deploy directly to _Kubernetes_ or _Azure Container Registry_.

# Agenda

**In this notebook** we will demonstrate the following topics:<br>

<img src="https://i.imgur.com/7yofoyJ.png" style="width:1800px"/> <br>

#### Step 1: Load our exploration dataset into a DataFrame
In this case, we'll be using the "[Inside Airbnb](http://insideairbnb.com/get-the-data.html)" dataset, and loading it from a csv from an Azure Storage Container.

#### Step 2: Perform basic exploratory analysis
Like plotting on a heatmap to get a better sense of the data.

#### Step 3: `Tracking` Demo: Random Forest Experiment
We perform multiple experiments using scikit-learn's Random Forest Regressor and log the models on MLflow to demonstrate the tracking capabilities.

#### Step 4: `Projects` Demo: Package up a Random Forest model as a Project
We will define these components that makes up an MLflow Project.:
- **MLProject** file
- **Conda** file
- **Run** script <br>

We will also load and run a Project straight from git to demonstrate git integration capabilities.

#### Step 5: `Model Management` Demo: Explore model flavors and framework abstraction capabilities
We explore the power of model flavors and framework abstraction capabilities available with MLflow models.

#### Step 6: `Production Serving` Demo: Containerize the trained model and deploy to Azure Container Instances
We will build a _Docker Container Image_ for a trained model and deploy to _Azure Container Instance_ (can easily swap to Kubernetes as well).

#### Step 7: `Live scoring` Demo: Make a prediction against the live API endpoint
We use an _HTTP call_ and _Postman_ to make a prediction against a test payload.
