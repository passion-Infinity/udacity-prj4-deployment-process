## Pipeline

From the root of the project:
- `npm run frontend:install`    - To install frontend dependencies.
- `npm run frontend:build`      - To build the Angular/Frontend.
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
* Deploy
    - Setup Elastic Beanstalk CLI
    - Install AWS Elastic Beanstalk CLI.
    - Deploy the angualr app to S3 Bucket.
    - Deploy the nodejs server to AWS Elastic Beanstalk.