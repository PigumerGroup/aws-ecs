[![Build Status](https://travis-ci.org/PigumerGroup/aws-ecs.svg?branch=master)](https://travis-ci.org/PigumerGroup/aws-ecs)

AWS ECS
=======

# Create network, repository and cluster

```
$ BUCKET_NAME=<YOUR BUCKET NAME> sbt
sbt> awscfCreateBucket create-bucket-stackname
sbt> awscfUploadTemplates
sbt> awscfCreateStack vpc
sbt> awscfCreateStack alb 
sbt> awscfCreateStack ecr
sbt> awscfCreateStack ecscluster
sbt> awscfCreateStack ec2
```

# Build

```
sbt> docker:stage
sbt> docker:publishLocal
```

# Push to repository

```
sbt> awsecr::awsecrLogin
sbt> awsecrPush
```

# Run

```
sbt> awscfCreateStack http
```
