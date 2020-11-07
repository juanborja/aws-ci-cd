# Project to try AWS CI/CD with beanstalk

A very basic project to try and practice CI/CD on an AWS way using beanstalk cli. Consists in default express generator application with some configurations to AWS services integration.

Install the eb cli is mandatory. You can see how here:

* [eb cli](https://github.com/aws/aws-elastic-beanstalk-cli-setup)

## First approach (only with beanstalk)

I use an AWS example, it comes from a previously example and if you doesn't follow is necessary to initialize your express application at some point. You can do it just before **Update the application** with the express command (if is available at global scope)

* [AWS example](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_nodejs_express.html)

### Environment creation

``` eb create <environment_name> // Ex. eb create test``` 

### Environment deploy

``` eb deploy <environment_name> // Ex. eb deploy test```

A pretty cool thing is that you can create two branches Ex. test/prod and associate them with deploy environment

### Default environment/branch

```bash 
git checkout -b test
eb use test
```

```bash 
git checkout master
eb use production
```
Naw you can use directly eb deploy en each branch and the code on the branch will be deployed in the configured environment  

## Second approach (With pipeline)

Setup an AWS pipeline with Code Commit as source and beanstalk as deploy destination and when a new change is deployed to the repository the pipeline starts to running. 

## Third approach (Codebuild integration)

WIP