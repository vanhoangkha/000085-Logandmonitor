---
title : "Clean up resources"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
1. Empty S3 bucket
- Open the console of [AWS S3](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-1)
- Select **fcj-book-store**
- Press **Empty**
- Enter **permanently delete**
- Press **Empty**
- Do the same with buckets starting with **aws-sam-cli-managed-default-** and bucket **book-image-resize-store**
2. Delete pipeline
- Open the console of [AWS CodePipeline](https://ap-southeast-1.console.aws.amazon.com/codesuite/codepipeline/pipelines?region=ap-southeast-1)
- Select pipeline **fcj-book-store-frontend-pipeline**
- Press **Delete pipeline**
- Enter **delete**
- Press **Delete**
- Do the same with the remaining pipelines
3. Clear stack of CloudFormation and CodeCommit repository
- Run the command below:
```
aws codecommit delete-repository --repository-name fcj-book-store-backend
aws codecommit delete-repository --repository-name fcj-book-store-frontend
sam delete --stack-name fcj-book-store-backend-dev
sam delete --stack-name fcj-book-store-backend
sam delete --stack-name aws-sam-cli-managed-dev-pipeline-resources
```