# django-application-deployment

## PART1

the first thing we did we chose our project from the given list of projects from exadel which was the main part. the project had to be new.
we chose an API that has been developed using the Django Framework. The API is connected to a postgresql database which stores information about people who 
plans to travel together. 

## PART 2

We made a Github  repository. We chose github mainly for CI/CD we both agreed because we like Github CI. 
the CI contains one  job the which contains steps to build a dockerfile and push to dockerhub from which the image will be pulled to deploy our kubernetes manifest.

## PART 3

Next big thing to talk about is Kubernetes. We used the AWS EKS cluster, using terraform for automating the creation. We choosed to use EKS due to all the heavy lifting
that has been done which includes logging, configuring ingress and and egress, loadbalancers. We installed kubectl and eksctl inside the ec2 instance that allows us run
commands against the cluster.

## PART 4

For monitoring, we used the helm package manager to install prometheus and grafana for visualization and integrated it our cluster.

## PART 5: Backup

This app stores data in a postgresql database. Therefore, we spinned up a postgresql RDS database in AWS and configured to do backups and take snapshots of the data
stored in the database. We also integrated with with cloudwatch to monitor for memory usage.





# HOW TO DEPLOY THE APPLICATION FROM SCRATCH

__PREREQUISITES__

a. AWS account
b. create an iam profile using this command `aws iam create-user --user-name terraform`

 __ARCHITECTURE__


![AWS Kubernetes nodes with EKS](https://user-images.githubusercontent.com/99150197/182565764-7d820f8c-9ae2-4bf5-81af-f3cc0520dce8.png)

#### Follow these steps:

1. `git clone git@github.com:Frankpromise/django-application-deployment.git`

2. `cd terraform-aws`

3. `terraform apply --auto-approve` This command will deploy and create the EKS Cluster in AWS.




