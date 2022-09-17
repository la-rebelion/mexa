---
layout: article
title: Deploying Complex Kubernetes Applications A Guide for Mortals
abstract: "People are spending more time figuring out how to deploy kubernetes applications than building their product! there is an easier way to deploy, upgrade and replicate these deployments in different environments."
eyeCatcher: https://images.unsplash.com/photo-1553002401-c0945c2ff0b0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=435&q=80
references:
  photo:
    from: Eileen Pan
    url: https://unsplash.com/@eileenp?utm_source=la-rebelion&utm_medium=referral
    source: unsplash
  articles:
    url: https://helm.sh/docs/topics/charts/
    text: Helm Charts
categories: helmee
tags: cloud devops helm
cta:
  description: "Would you like learn more about helmee? Subscribe and be notified when alpha version is open to test"
  short_text: Subscribe to our alpha testers list
  destination: https://www.patreon.com/rebelionlabs
---

It's frustrating that there is so much information out there on how to deploy to Kubernetes with `helm`, but nothing on the actual steps. People are spending more time figuring out how to deploy than building their product! This guide will walk you through the steps of deploying a simple application to Kubernetes using Helm. We’ll also cover some best practices for making sure your deployment stays up-to-date with the latest changes in your codebase.

Deploying complex applications across multiple environments is hard, and time consuming. There has to be a better way! Helm is the solution to this problem! It allows you to package your application as a chart and deploy it with one command. Helm integrates with many popular tools, like Jenkins and Gitlab CI/CD, so you don’t have to worry about running into issues when deploying complex applications across multiple cloud providers.

But, `helm` as a solution to this problem **is just a promise**, deploying applications with `helm` is slow and tedious, because the *Helm chart* is a complex file structure that needs to be built and stored in a version control system. In order for your application to be deployed, the *Helm chart* needs to be built on every node in your cluster (by default). This can take anywhere from 10 minutes up to an hour depending on how many resources are available.

Deploying applications with `helm` is a pain. It is too slow and unwieldy. It creates more work than it saves, and wastes resource (time, effort, money) that could be better spent on other things. It is time-consuming, and it makes it difficult to iterate quickly on your application’s architecture. That's why we create `helmee`, a simple, fast and easy to use tool for deploying applications on Kubernetes. Helmee makes it easy to provision a new application in different Kubernetes cluster instances, deploy it instantly with Helm chart or git repo, and then tear down the entire application when you need to move on.

Why is that important?

Helm is a package manager for Kubernetes. It allows you to install new applications into your cluster, and also provides the ability to upgrade or downgrade those applications if needed.

It’s a great tool that enables many useful features like rolling upgrades, canary deployments (instantly test new versions of your application before rolling them out), blue/green deployments (redeploying only affected pods when updating applications) and more.

But all that is only possible for a single cluster; have you tried to replicate the deployment of complex `helm` charts to a different environment? To many variables and files to modify!

No worry, Helmee is here to automate those deployments!
