---
layout: post
title: Continous integration setup
published: true
---

# 2018-01-24-CI-Continuous-integration

## One repo or multiple repos

* One repo better [https://nrwl.io/nx/why-a-workspace](https://nrwl.io/nx/why-a-workspace)
* One or multiple in the context of micro-services [https://medium.com/@somakdas/code-repository-for-micro-services-mono-repository-or-multiple-repositories-d9ad6a8f6e0e](https://medium.com/@somakdas/code-repository-for-micro-services-mono-repository-or-multiple-repositories-d9ad6a8f6e0e)
* Mono repository for micro service [http://blog.shippable.com/our-journey-to-microservices-and-a-mono-repository](http://blog.shippable.com/our-journey-to-microservices-and-a-mono-repository)

## What is Continuous integration / Continuous deployement

Continuous Integration \(CI\) : Push changes on developement server quickly and automatically so new changes can be tested earlier

Continous Deployement \(CD\) : Push changes on production server quickly and automatically so new changes can benefits to users earlier

All the infos here [https://www.thoughtworks.com/continuous-integration](https://www.thoughtworks.com/continuous-integration)

The most important being :

The practice

* Maintain a single source repository
* Automate the build
* Make your build self-testing
* Every commit should build on an integration machine
* Keep the build fast
* Test in a clone of the production environment
* Make it easy for anyone to get the latest executable version
* Everyone can see what’s happening 
* Automate deployment

How to do it

* Developers check out code into their private workspaces
* When done, commit the changes to the repository
* The CI server monitors the repository and checks out changes when they occur
* The CI server builds the system and runs unit and integration tests
* The CI server releases deployable artefacts for testing
* The CI server assigns a build label to the version of the code it just built
* The CI server informs the team of the successful build
* If the build or tests fail, the CI server alerts the team
* The team fixes the issue at the earliest opportunity
* Continue to continually integrate and test throughout the project

Team responsibilities

* Check in frequently
* Don’t check in broken code
* Don’t check in untested code
* Don’t check in when the build is broken
* Don’t go home after checking in until the system builds

## Which CI server to choose

A comparison of continuous integration tools

[https://www.code-maze.com/top-8-continuous-integration-tools/](https://www.code-maze.com/top-8-continuous-integration-tools/)

* Amazon AWS tutorial for contiuous integration 

  [https://docs.aws.amazon.com/codepipeline/latest/userguide/tutorials.html](https://docs.aws.amazon.com/codepipeline/latest/userguide/tutorials.html)

