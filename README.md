![CodeBuild](https://codebuild.ap-northeast-1.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoib05lbU1DaTRKcktYbFN3WjFCRVV0cVVMRTVqUjVsaHpTWVdsRDE3N2NMaDNuZ0dMTmJ1T0V5VlZPbG5QcWprR0Rqd0JqQy9zc095UEFqY0FCd3NjZkswPSIsIml2UGFyYW1ldGVyU3BlYyI6IjZ4TEVweVRSalpLbFUzSnEiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=master)

AWS ECS
=======

# Create network, repository and cluster

```
$ BUCKET_NAME=<YOUR BUCKET NAME> sbt
sbt> awscfCreateBucket create-bucket-stackname
sbt> awscfUploadTemplates
sbt> awscfCreateStack iam
sbt> awscfCreateStack ecr
sbt> awscfCreateStack codebuild
sbt> awscfCreateStack vpc
sbt> awscfCreateStack alb 
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
