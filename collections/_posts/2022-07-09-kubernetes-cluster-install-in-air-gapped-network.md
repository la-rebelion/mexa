---
layout: article
title: Kubernetes Cluster Installation In an Air Gapped Network
abstract: "Installing a Kubernetes cluster is not a simple tasks, and is even harder when you don't have access to the Internet. Here I explain how to do it easily."
eyeCatcher: https://images.unsplash.com/photo-1463567517034-628c51048aa2?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80
categories: [Air Gapped Network, Kubernetes]
tags: [cloud, kubernetes]
cta:
  description: "Are you interested on getting the notes with commands?:"
  short_text: Join the community
  destination: https://www.patreon.com/rebelionlabs
youtube_id: f71Z6SVzhVg
# depending on the video provided, the id variable can be: youtube_id, vimeo_id... etc. Ref: https://github.com/nathancy/jekyll-embed-video
---

## Cluster Details in This Lab Deployment

Kubernetes --- v1.24.3  
Docker Container Runtime --- v20  
Flannel Container Networking --- v0.19.0  
Nginx Ingress Networking --- v1.3.0  
etcd --- v3.5.3  
CoreDNS --- v1.8.6  

## Kubernetes Cluster Installation In an Air Gapped Network on Ubuntu 22.04 (Jammy)

This is NOT a tutorial to install Kubernetes locally for testing or development purposes, this hands-on lab is for System Integrators, SysAdmins or any technical Engineers that need to **setup a cluster on customer premises**, a real or near-real environment to a carrier grade environment level, where Enterprise projects requires  extremely reliable, well tested and proven in its capabilities. If you need a local testing environment, you should try minikube instead, and there are lots of tutorials for that.

The **pain point** in these kind of environments is that are highly secured trusting NOTHING, resulting in isolated segment of networks that difficult the SME life, you know what I am talking about. If that is you case, then watch and follow this hands-on tutorial.

{% include elements/video-player.html style="primary" %}

Any Linux package manager performs dependency resolution when installing, updating, and removing software packages, but if you don't have Internet access, you need to install packages manually one by one. This is a very difficult, and tedious task when there is no Internet access to the repositories, difficulty relies on the fact that RPMs may have many dependencies and you need to download each of this one by one, sometimes in a trial an error approach.

The _secret_ to install a Kubernetes cluster in a network when you don't have Internet access (air gapped network) is to download ALL the required images in your local PC, then, just copy and deploy those images in the Master node(s) and Worker node(s). There are two approaches here, doing so in a (1) container, mounting a volume to copy all downloaded files after completion of all dependencies downloaded; or doing so on a VM (2) that eventually you can deploy in the customer premises.

This Lab is assuming the VM is provided by customer, for that, I suggest to do it following the container approach if you have Docker installed locally, or you can do it easily within a VM if you have [multipass](https://multipass.run/docs/tutorials) installed, but if you need to provide the _qcow2_ image to the customer and deploy it, then, the VM is much better, because it will be only a matter of deploying and create replicas of this VM.

With multipass, you can create a completely new Linux VM with one command line! "Multipass is the recommended method to create Ubuntu VMs on Ubuntu. It's designed for developers who want a fresh Ubuntu environment with a single command"

### Multipass Installation guides

* https://snapcraft.io/install/multipass/centos
* https://multipass.run/docs/installing-on-linux
* https://ubuntu.com/server/docs/virtualization-multipass
* https://github.com/canonical/multipass

{% include elements/button.html style="primary" %}

GiHub repository with the commands:  
