# Udagram

- [Udagram](#udagram)
  - [Description](#description)
    - [Dependencies](#dependencies)
    - [AWS Cloud Setup](#aws-cloud-setup)
  - [Environment Variables](#environment-variables)
  - [Pipeline](#pipeline)
  - [CircleCi](#circleci)
  - [Testing](#testing)
    - [Unit Tests:](#unit-tests)
    - [End to End Tests:](#end-to-end-tests)
  - [Built With](#built-with)

---

## Description
A more in depth documentation into the application.

### Dependencies

```
- Node v14.15.0 (LTS) or more recent. While older versions can work it is advisable to keep node to latest LTS version
- npm 6.14.8 (LTS) or more recent, Yarn can work but was not tested for this project
- AWS CLI v2, v1 can work but was not tested for this project
- AWS EB CLI
- AWS RDS database running Postgres.
- AWS S3 bucket for Frontend.
- AWS Elastic Beanstalk for Backend.
```

### AWS Cloud Setup

- RDS - Database Host: hostingapp.cxkpb2ofq1gm.us-east-1.rds.amazonaws.com
- RDS - Database Port: 5432
- RDS - Database Name: hostingapp

- S3 Endpoint - Frontend: http://hostingapp-651394723136-bucket.s3-website-us-east-1.amazonaws.com

- Elastic Beanstalk URL - Backend: http://udagram-api-dev222.us-east-1.elasticbeanstalk.com

## Environment Variables

Setup the following variables in the .env file or in the cloud environments:
```
- PORT                = 8080
- POSTGRES_HOST       = <Database_IP_Address>
- POSTGRES_PORT       = <Database_Port>
- POSTGRES_DB         = <Database_Name>
- POSTGRES_USERNAME   = <Database_Username>
- POSTGRES_PASSWORD   = <Database_Password>
- URL                 = <Url>
- JWT_SECRET          = <Any_PassPhrase>
- AWS_REGION          = <us-east-1>
- AWS_PROFILE         = <Profile>
- AWS_BUCKET          = <Bucket_Name>
```

## Pipeline

From the root of the project:
- `npm run frontend:install`    - To install frontend dependencies.
- `npm run frontend:build`      - To build the Angular/Frontend.
- `npm run frontend:lint`       - To format project.
- `npm run frontend:start`      - To start angular project.
- `npm run frontend:test`       - To test the Angular/Frontend.
- `npm run frontend:deploy`     - To deploy the project to S3 using `./udagram-frontend/bin/deploy.sh` deploy script.
- `npm run backend:install`     - To install backend dependencies.
- `npm run backend:start`       - To udagram api.
- `npm run backend:build`       - To transpile the Typescript/Backend.
- `npm run backend:deploy`      - To deploy the project to EB using `./udagram-api/bin/deploy.sh` deploy script.


## CircleCi

The order of the run jobs:
* Build
    - Setting ENV Variables.
    - Install NodeJS.
    - Checkout Code & Cloning the Repo.
    - Frontend:
        - Install dependencies.
        - Build the angular.
    - Backend:
        - Install dependencies.
        - Build the api.
* Approval Holding (Need to approve to move next step deploy)
* Deploy
    - Setup Elastic Beanstalk CLI
    - Install AWS Elastic Beanstalk CLI.
    - Setup Env for Elastic Beanstalk Env
    - Deploy the angualr app to S3 Bucket.
    - Deploy the nodejs server to AWS Elastic Beanstalk.

## Testing

This project contains two different test suite: unit tests and End-To-End tests(e2e). Follow these steps to run the tests.

1. `cd udagram-frontend`
2. `npm run test`
3. `npm run e2e`

There are no Unit test on the back-end

### Unit Tests:

Unit tests are using the Jasmine Framework.

### End to End Tests:

The e2e tests are using Protractor and Jasmine.

## Built With

- [Angular](https://angular.io/) - Single Page Application Framework
- [Node](https://nodejs.org) - Javascript Runtime
- [Express](https://expressjs.com/) - Javascript API Framework