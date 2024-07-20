# Overview

This [bitbucket-pipelines.yml](https://github.com/Linuxander/CI_CD_Bitbucket_Pipline_React_AWS/blob/main/bitbucket-pipelines.yml) file is an example on how to implement Continuous Integration and Continuous Deployment Bitbucket pipeline triggers for a React project that is deployed on the AWS Cloud Platform.

## AWS Pipeline Steps Explination

There are two critical AWS related pipeline steps in this file.
1. Syncing the build contents to the target Amazon S3 bucket specified
2. Invalidating the Amazon CloudFront cache so that users are presented with the latest content.  Otherwise, they may be looking at old cached content even though the S3 bucket contains the latest.

## Bitbucket Variables for Contentful CMS API & AWS Account

My React website leverages Contentful CMS API which is where it gets its dynamic content from.  You will notice that two [Contentful CMS Bitbucket variables](https://github.com/Linuxander/CI_CD_Bitbucket_Pipline_React_AWS/blob/main/bitbucket-pipelines.yml#L19) which are exported into a .env file so that Bitbucket can include them during the React build process.


You will also notice a few AWS related Bitbucket variables which include the credentials for the pipeline to connect to my AWS account to peform its changes.

## Replace Amazon S3 Bucket Name

If you plan to use this script for your own React + AWS project, make sure to [replace the placeholder name for your actual S3 bucket name](https://github.com/Linuxander/CI_CD_Bitbucket_Pipline_React_AWS/blob/main/bitbucket-pipelines.yml#L26).

