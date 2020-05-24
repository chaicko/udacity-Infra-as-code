# udacity-Infra-as-code
Solution for the second project on Infrastructure as Code of the Udacity DevOps Nanodegree

# Requirements
 - Python

# Setup

## Install requirements

```
pip install -r requirements.txt dev-requirements
```

## Setup aws cli
```
aws configure
```

## WebApp

The Udagram developers will be uploading their code to an S3 Bucket. We create an S3
bucket using CloudFormation as well. They wanted to automate the deployment of the so some
tools were written for them:

They decided to use a bucket named `udacity-project2` where the Udagram code was uploaded.
```
```

# Creating stacks

## S3 WebApp hosting

The DevOps team created a stack for the Web developers to upload their code:

```
$ ./create-update-stack UdagramDevelopersStack scripts/developers.yml scripts/developers-parameters.json

Stack "UdagramDevelopersStack" does not exist, creating...
```

The Web developers do their coding in the `webapp` directory of this repository.
Once ready, they deploy it using the following:

```
./deploy-webapp
```

## Infrastructure

### Network

Create the Network infrastructure with

```
./create-update-stack UdagramProductionNetwork scripts/network.yml scripts/network-parameters.json
```

### Servers

Updating the stacks adding into it the servers:
```
./create-update-stack UdagramProductionServers scripts/server.yml scripts/server-parameters.json
```
