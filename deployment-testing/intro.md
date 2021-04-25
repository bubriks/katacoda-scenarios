This tutorial will focus on showcasing the basics of CI/CD pipeline implementation and the product's A/B testing.

# What is CI/CD

CI/CD is a software development practice of "continuous integration" and either "continuous delivery" or "continuous deployment".
- Integration: changes are merged into a common repository and usually tested.
- Delivery: expands on continuous integration, by deploying the solution in a testing environment.
- Deployment: like delivery, but automatically delivers the newest change to the customer.

# What is A/B testing?

A/B (Alpha/Beta) testing is a testing methodology used by developers that involves monitoring the user behavior in order to help improve the product.
The basic idea is to present users with two variations of the same solution and see which one performs best.

# Plan for the tutorial

This tutorial will be divided into few parts, with the user being able to skip specific sections if they are not interested in them (Step 1 is mandatory).

- Step 1: Getting started (Prerequisite for the rest of the tutorial).
- Steps 2 to 4: Focus is placed on understanding the basic principles of the CI/CD pipeline using Travis.
- Steps 5 to 7: Implementation of A/B testing. This will include the usage of 2 versions of the same website. With each of them offering different colors for buttons. The goal is to monitor the impact of the colors on the consumer. 

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
