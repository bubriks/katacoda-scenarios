This tutorial will focus on showcasing the basics of CI/CD pipeline implementation and products A/B testing.

# What is CI/CD

CI/CD is a software development practice of "continuous integration" and either "continuous delivery" or "continuous deployment".
During the integration, phase changes are merged into a common repository and usually tested.
Meanwhile, continuous delivery expands on continuous integration, by deploying the solution in a testing environment.
The deployment automatically delivers the newest change to the customer.

# What is A/B testing?

A/B (Alpha/Beta) testing is a testing methodology used by developers that involves monitoring the user behavior in order to help improve the product. The basic idea is to present users with two variations of solution and see which one performs best.

# Plan for the tutorial

The tutorial will be divided into 2 parts.

The first part of this tutorial focuses on understanding the basic principles of the CI/CD pipeline using Travis.

The following section of the tutorial will implement A/B testing. This will include the usage of 2 versions of the same website. With each of them offering different colors for the button. The goal is to monitor which of the colors (if any) encourage the button to be clicked more often. 

# Learning goals:
* CI with Travis CI
* A/B Testing
* Traffic management with Istio
* Using docker containers with Kubernetes
* Solution monitoring

# Requirements:
* GitHub account
* Travis CI account

# More information

If you would like to learn more about this project, feel free to explore the repository which we will be using throughout this tutorial.

[Simple-web](https://github.com/bubriks/simple-web)
