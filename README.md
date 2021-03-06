# config-rule-status

## What it Does
- Setup resource monitoring using AWS Config.
- Create security compliance rules using AWS Config Rules, including both AWS-managed and custom rules.
- Create AWS Lambda functions that implement infrastructure security tests (for the custom rules).
- Create an AWS Lambda function to aggregate the Config Rule compliance statuses and return an overall "PASS" or "FAIL".  This function is designed to be used as a Security Integration Test as part of a CD pipeline.
- Provide a CLI (via gulp) for creating and updating the associated resources in AWS.

## Installation
**Prerequisites**
```
aws cli
npm install --global serverless@0.5.5
npm install --global gulp-cli

```

**Clone the source and set environment variables**
```
==> git clone https://github.com/stelligent/config-rule-status.git
```

**Install packages and configure:**
```
==> cd config-rule-status
==> npm install
```

**Initialize the project:**
```
==> gulp init \
--region us-east-1 \
--stage prod \
--name config-rule-status \
--awsProfile yourProfileName \
--email user@company.com
```

**Build the project:**
```
==> gulp build
```

## Execution

**Run Tests**
```
==> gulp test:local
```

**Deploy to AWS**
```
==> gulp deploy:lambda --stage prod --region us-east-1
==> gulp deploy:config --stage prod --region us-east-1
```

**Verify Deploy and/or Integrate into a CD pipeline**
```
==> gulp verify --stage prod --region us-east-1
```

**View Lambda logs**
```
==> gulp logs --stage prod --region us-east-1 --functionName cidrIngress --duration 1d
```

## Modifying

**Create Additional Stages, Regions, and Functions**

Use the Serverless CLI to add new configurations and functionality:
http://docs.serverless.com/docs/commands-overview
