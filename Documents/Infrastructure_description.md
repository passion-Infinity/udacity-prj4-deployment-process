### AWS SERVICES
- AWS RDS (DATABASE)
- AWS ELASTIC BEANSTALK (SERVER)
- AWS S3 BUCKET (STATIC WEBSITE HOST)

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