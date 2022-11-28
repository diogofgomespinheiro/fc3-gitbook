# Introduction

## <mark style="color:purple;">What it is?</mark>

[Kubernetes](https://kubernetes.io/docs/concepts/overview/), also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.

It groups containers that make up an application into logical units for easy management and discovery. Kubernetes builds upon [15 years of experience of running production workloads at Google](http://queue.acm.org/detail.cfm?id=2898444), combined with best-of-breed ideas and practices from the community.

## <mark style="color:purple;">Key points</mark>

* Kubernetes is available through a set of APIs
* Usually this APIs are accessed through a CLI: kubectl
* Everything is based on state.
* Kubernetes Master
  * kube-apiserver
  * kube-controller-manager
  * kube-scheduler
* Another nodes:
  * kubelet
  * kubeproxy

## Dynamic (superficial)

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
