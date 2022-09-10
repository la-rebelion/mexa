---
layout: article
title: Blue Green or Canary Rollout for Kubernetes Helm based deployments
abstract: "How to implement a rollout strategy on top of Kubernetes or helm deployments?"
eyeCatcher: https://images.unsplash.com/photo-1489380988310-a781a51cd48b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1472&q=80
categories: Kexal
tags: cloud devops
properties: pinned
---

huixti de dos colores

## Challenges and Restrictions

* The first restriction is that the cluster administrator may not allow the application owner to create CRDs without passing a certification process. Sometimes this process doesn't even exist or takes too much time to be approved.
* Security constraints
* Role and cluster Restrictions - limited to namespace only
* 

## Assumptions

* Namespace is defined and created by customer (sysadmin)
* Your user role is not granted to create CRDs
* "[Zero trust network access (ZTNA)](https://www.gartner.com/en/information-technology/glossary/zero-trust-network-access-ztna-)" environment where the applications are hidden from discovery, and access is restricted; hence, you won't have access to the minimum resources you need, i.e.: Git (GitHub or GitLab), public image Containers registry, then, installation and configuration is harder because you need to tweak the "standard" product deployment scripts.

![focus on single task](https://images.unsplash.com/photo-1489380988310-a781a51cd48b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1472&q=80)

Image [source](https://unsplash.com/@randytarampi)

## What is

_Kexal_ is a tool ...

## Why _Kexal_

> "If you want better results, then forget about setting goals. [Focus on your system instead][1]."

_Kexal_ ...

## Integrations

* [Keep](https://www.google.com/keep/)
* [Trello](https://trello.com)
* [Notion](https://www.notion.so)

If you find this project useful, please star our repository in GitHub, follow us on Twitter and subscribe for latest news. Thanks.

---

References:

* [Procrastination](https://jamesclear.com/procrastination)

[1]: <https://jamesclear.com/goals-systems> "Forget About Setting Goals. Focus on This Instead."

Images:

* [Focus](https://unsplash.com/@rvignes)
