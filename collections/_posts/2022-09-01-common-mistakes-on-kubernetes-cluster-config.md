---
layout: article
title: Common Mistakes on Kubernetes cluster config
abstract: "I have seen these mistakes, or misunderstanding several times and almost ALWAYS when people is starting to work on clusters with more than one worker node, so I thought it would be useful to share them with you."
eyeCatcher: https://images.unsplash.com/photo-1655720840699-67e72c0909d1?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1567&q=80
categories: [Kubernetes]
tags: [cloud, kubernetes, sysadmin]
cta_description: "Would you like more articles and videos? Subscribe and be notified when more material is available"
cta_short_text: Subscribe to our articles and social media
cta_destination: https://www.patreon.com/rebelionlabs
youtube_id: GIt8dn99JZ4
# depending on the video provided, the id variable can be: youtube_id, vimeo_id... etc. Ref: https://github.com/nathancy/jekyll-embed-video
---

## Introduction

Kubernetes is a container orchestration platform, which means it manages and tasks containers across infrastructure. However, I have seen these mistakes, or misunderstanding several times and almost ALWAYS when people is starting to work on clusters with more than one worker node, so I thought it would be useful to share them with you, I hope this clarifies the misunderstanding to avoid repeating same error over and over.

## Video

{% include elements/video-player.html style="primary" %}

Every kubernetes cluster has **at least** one worker node, one master only or one master and one worker node (common for dev/local tests), this is OK if a user prefers to push container images directly to the (single) worker node... but, what happens when more nodes come into the picture?

First, let's understand that kubernetes is NOT a replacement for Docker or any other container registry, it **requires one**. Kubernetes is the cluster manager that makes it possible to run applications on multiple hosts in the same cluster. It’s important to understand that kubernetes is not just a container orchestrator; it is a full-fledged platform for managing containers across multiple machines, whereas Docker (and other container orchestrators) provide more limited functionality.

"As a distributed system, the architecture of Kubernetes is flexible and loosely-coupled, with a control plane for managing the overall cluster, and the data plane to provide capacity such as CPU, memory, network, and storage so that the containers can run and connect to a network."

The Container Runtime Interface (CRI) is the main protocol for the communication between the `kubelet` and Container Runtime. "You need a working container runtime **on each Node in your cluster**, so that the `kubelet` can launch Pods and their containers" - this is the key, and where the main problem relays.

A common mistake when using Kubernetes cluster configuration files when compared with Docker ones is confusing "container orchestration" with "container management" or "container management platform"; this means that many people may think they need something like Docker Swarm or Mesos when what they really need is just some sort of "containers", a **container registry**.

Kubernetes was designed to orchestrate (deploy/maintain) several small containers and applications a in a cluster environment, what means that the purpose of Kubernetes is to manage containers across several machines not only one, like docker-compose or minikube.

In order for you to enable all the nodes in the cluster to create the Pods successfully without container image pulling errors, you must configure the following parameters:

1. Repository from where you are going to pull the images. A private registry is the solution in case your cluster does not have access to the public cloud; which is common on Enterprise projects.
2. Be sure that the Pod manifest is pointing to the correct registry.
3. Ensure that your namespaces have appropriate authorization to pull images from your local/private registry.

## Problem and Solutions

**Problem:** ImagePullBackOff

**Solution:** Create a secret with login credentials.

`kubectl create secret docker-registry regcred --docker-server=<private-reg-container> --docker-username=<your-name> --docker-password=<your-pword> --docker-email=<your-email>`

**Solution A:** Create a [Pod manifest](https://raw.githubusercontent.com/kubernetes/website/main/content/en/examples/pods/private-reg-pod.yaml) that uses your Secret

**Solution B:** Patch `namespace` Service Account with the secret:

`kubectl patch serviceaccount default -p '{"imagePullSecrets": [{"name": "regcred"}]}' -n my-app-ns`

Be careful when configuring your kubernetes cluster nodes.

## Conclusion

In this article we learned about what Kubernetes requires to pull images from a local/private container registry. We also learned about the mistakes that people make when configuring their cluster nodes. If you are new to Kubernetes please read this article before setting up your kubernetes cluster!

## References

* [Kubernetes Components](https://kubernetes.io/docs/concepts/overview/components/)
* [What is the Kubernetes Data Plane?](https://spot.io/what-is-kubernetes-data-plane)
* [Container Runtime Interface (CRI)](https://kubernetes.io/docs/concepts/architecture/cri/)
* [Add ImagePullSecrets to a service account](https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/#add-imagepullsecrets-to-a-service-account)
* [Pull an Image from a Private Registry](https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/)
* Configuring nodes to authenticate to a private registry [Use Cases](https://kubernetes.io/docs/concepts/containers/images/#use-cases)
* [How to fix ErrImagePull and ImagePullBackoff](https://komodor.com/learn/how-to-fix-errimagepull-and-imagepullbackoff/)

Picture from [DeepMind](https://unsplash.com/@deepmind?utm_source=la-rebelion&utm_medium=referral) at unsplash
