# Udagram Image Filtering Application

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.


### Prerequisite
1. The depends on the Node Package Manager (NPM). You will need to download and install Node from [https://nodejs.com/en/download](https://nodejs.org/en/download/). This will allow you to be able to run `npm` commands.
2. Environment variables will need to be set. These environment variables include database connection details that should not be hard-coded into the application code.
3. [Kubernetes command-line tool](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

Note: You can also use [Travis CI tool](https://docs.travis-ci.com/user/tutorial/) but don't forget to modify the [`.travis.yml`](./.travis.yml) file. 
#### Environment Secrets
To set environment variables, you may want to use [secrets](https://kubernetes.io/docs/tasks/inject-data-application/distribute-credentials-secure/).


### Database
Create a PostgreSQL database either locally or on AWS RDS. Set the config values for environment variables prefixed with `POSTGRES_` in your [secret](https://kubernetes.io/docs/tasks/inject-data-application/distribute-credentials-secure/).

### S3
Create an AWS S3 bucket. Set the config values for environment variables prefixed with `AWS_` in your [secret](https://kubernetes.io/docs/tasks/inject-data-application/distribute-credentials-secure/).


### How to run the App
1. Access your Kubernetes cluster using `kubectl`.

2. Navigate into: [udagram-feed-api](./udagram-feed-api), [udagram-user-api](./udagram-user-api), [udagram-frontend](./udagram-frontend),[udagram-reverseproxy](./udagram-reverseproxy).

3. In each directory run:
```bash
kubectl apply -f deployment.yml 
kubectl apply -f service.yml
```