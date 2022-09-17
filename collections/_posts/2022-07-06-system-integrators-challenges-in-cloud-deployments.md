---
layout: article
title: Challenges for Software Vendors and System Integrators
abstract: "Air gapped network or Zero Trust Network Access (ZTNA) add complexity for cloud system integrators delivery projects on customer premises"
eyeCatcher: https://images.unsplash.com/photo-1578328819058-b69f3a3b0f6b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1374&q=80
categories: [Air Gapped Network, Zero Trust Network Access (ZTNA)]
tags: cloud devops security
cta:
  description: "DevOps, SysAdmin, Cloud... how to survive the SI journey?:"
  short_text: Follow my steps here
  destination: https://mexa.rebelion.la
youtube_id: _57CUWCyoXo
# depending on the video provided, the id variable can be: youtube_id, vimeo_id... etc. Ref: https://github.com/nathancy/jekyll-embed-video
---

## Challenges for Software Vendors and System Integrators

{% include elements/video-player.html style="primary" %}

Air gapped network or Zero Trust Network Access (ZTNA), is a security concept concentrating on the belief that organizations should not automatically trust anything inside or outside its perimeters, and verify anything trying to connect to the systems before granting access; this is a best practice, because isolates segment of networks and secure services eliminating threats… but, whether you are a System Integrator or Independent Software Vendor, you will need to integrate with multiple products from other vendors or IT systems in the customer infrastructure.

Well, the whole point and focus about the ideas and tools that I will share on these multiple posts and videos of the channel is around this restriction on enterprise projects, where you are limited to work in a “jailed” environment, and you still need to work in silos!

What do I mean? Even when several vendors are working altogether to deliver a cloud solution to a customer in common, each vendor use specific tools for their products, and that is because each vendor’s restrictions, or enterprise licenses, agility, best practice processes or any other matter; what happen when a vendor needs to deploy its own part in an environment that they don’t have control at all, I mean, this vendors do not have admin privileges on a Kubernetes cluster or OpenShift environments, all networks and the traffic on those networks have particularities that eventually would affect your fine tuned process.

Why?... Just because Murphy is always present, and yes, your pipeline will be broken due to this lack of access to external networks and services… forget about GitHub, or GitLab, or Jenkins, harness, Docker registry, you need to be prepared to adapt easily to the rules of this jungle and survive with the less injuries.

{% include elements/button.html style="primary" %}
