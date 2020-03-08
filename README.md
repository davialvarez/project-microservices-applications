# Udacity Capstone Microservice Application 
> Swagger API applications over Kubernetes.

CI/CD pipeline for micro services applications (Swaggerapi) with rolling deployment over Kubernetes. 

![](header.png)

## Features

In this project the following skills apply:

- Working in AWS
- Using Jenkins to implement Continuous Integration and Continous Deployment
- Building pipelines
- Working with CloudFormation to deploy clusters
- Building Kubernetes clusters
- Building Docker containers in pipelines

## Installation

### Prerequisites

- Docker
- Kubernetes (AWS EKS)
- CloudFormation
- Jenkins
- Python
- aws-cli
- kubectl

Linux:

1. First create Kubernetes EKS 
```sh
cd cluster-kubernetes
./create.sh Iam-Capstone iam.yml
./create.sh Vpc-Capstone vpc.yml
./create.sh Eks1-Capstone eks1cluster.yml
```

2. Update ARN role
```sh
```

3.
```sh
aws eks update-kubeconfig --name Cluster-Capstone-eks
kubectl apply -f aws-auth-cm.yaml
```

## Usage example

A few motivating and useful examples of how your product can be used. Spice this up with code blocks and potentially more screenshots.

_For more examples and usage, please refer to the [Wiki][wiki]._

## Development setup

Describe how to install all development dependencies and how to run an automated test-suite of some kind. Potentially do this for multiple platforms.

```sh
make install
npm test
```

## Release History

* 0.2.1
    * CHANGE: Update docs (module code remains unchanged)
* 0.2.0
    * CHANGE: Remove `setDefaultXYZ()`
    * ADD: Add `init()`
* 0.1.1
    * FIX: Crash when calling `baz()` (Thanks @GenerousContributorName!)
* 0.1.0
    * The first proper release
    * CHANGE: Rename `foo()` to `bar()`
* 0.0.1
    * Work in progress

## Meta

Your Name – [@YourTwitter](https://twitter.com/dbader_org) – YourEmail@example.com

Distributed under the XYZ license. See ``LICENSE`` for more information.

[https://github.com/yourname/github-link](https://github.com/dbader/)

## Contributing

1. Fork it (<https://github.com/yourname/yourproject/fork>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request

<!-- Markdown link & img dfn's -->
[npm-image]: https://img.shields.io/npm/v/datadog-metrics.svg?style=flat-square
[npm-url]: https://npmjs.org/package/datadog-metrics
[npm-downloads]: https://img.shields.io/npm/dm/datadog-metrics.svg?style=flat-square
[travis-image]: https://img.shields.io/travis/dbader/node-datadog-metrics/master.svg?style=flat-square
[travis-url]: https://travis-ci.org/dbader/node-datadog-metrics
[wiki]: https://github.com/yourname/yourproject/wiki
