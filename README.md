# MLflow Tutorial



## Note: I am hiding all my personal credentials. If you are following my repository, please replace the dummy credentials with your actual credentials.

## For Dagshub:

MLFLOW_TRACKING_URI=https://dagshub.com/.......

MLFLOW_TRACKING_USERNAME=xyz...

MLFLOW_TRACKING_PASSWORD=6824692................

python script.py



```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/...........

export MLFLOW_TRACKING_USERNAME=xyz.....

export MLFLOW_TRACKING_PASSWORD=6824692...............


```


# MLflow on AWS

## MLflow on AWS Setup:

1. Login to AWS console.
2. Create IAM user with AdministratorAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on EC2 machine
```bash
sudo apt update

sudo apt install python3-pip

sudo apt install pipenv

sudo apt install virtualenv

mkdir mlflowvenv

cd mlflowvenv

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell


## Then set aws credentials
aws configure


#Finally 
mlflow server -h 0.0.0.0 --default-artifact-root s3://bucket_name

#open Public IPv4 DNS to the port 5000

# MLFlow Tracking URL of AWS
AWS_MLFLOW_TRACKING_URI=http://ec2-.................compute-1.amazonaws.com:5000/

#set uri in your local terminal and in your code 
export MLFLOW_TRACKING_URI=http://ec2-.............compute-1.amazonaws.com:5000/
```


