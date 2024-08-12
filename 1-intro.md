---
title: Intro
nav: true
---

# Introduction

In this workshop, we will learn how to deploy a LLM for a RAG application locally on your laptop! To setup a LLM application locally, we will be leveraging containerzation techniques. To give you a brief understanding of these concepts, we have described them at a high-level here.

## Containerization

Containers are technologies that allow the packaging and isolation of applications with their entire runtime environment—all of the files necessary to run. This makes it easy to move the contained application between environments (dev, test, production, etc.) while retaining full functionality. Containers are also an important part of IT security. By building security into the container pipeline and defending infrastructure, containers stay reliable, scalable, and trusted. You can also easily move the containerized application between public, private and hybrid cloud environments and data centers (or on-premises) with consistent behavior and functionality. There are different containerization tools you can use, some of them most popular ones are [Podman](https://docs.podman.io/en/latest/) and [Docker](https://www.docker.com/). For the purpose of this workshop, we will be using Podman.

### Podman

Podman (short for pod manager) is an open source tool for developing, managing, and running containers. Developed by Red Hat® engineers along with the open source community, Podman manages the entire container ecosystem using the libpod library.
Podman’s daemonless and inclusive architecture makes it an accessible, security-focused option for container management. Its accompanying tools and features, such as Buildah and Skopeo, let developers customize their container environments to suit their needs. Developers can also take advantage of Podman Desktop, a graphical user interface (GUI) for using Podman in local environments.

You can read more about Podman here: [https://www.redhat.com/en/topics/containers/what-is-podman](https://www.redhat.com/en/topics/containers/what-is-podman)

### What can you do with containers?

You can deploy containers for a number of workloads and use cases–big to small. Containers give your team the underlying technology needed for a cloud-native development style, so you can get started with DevOps, CI/CD (continuous integration and continuous deployment), and even go serverless.

Container-based applications can work across highly-distributed cloud architectures. Application runtimes middleware provides tools to support a unified environment for development, delivery, integration, and automation.

To learn more, check out this article [here](https://www.redhat.com/en/topics/containers)!

## LLM RAG Application


## AI Labs Recipes

The `ai-lab-recipes` repository is a collaboration of data scientists and application developers that brings together best practices from both worlds. The result is a set of containerized AI-powered applications and tools that are fun to build, easy to run, and convenient to fork and make your own.

AI Lab recipes started as the home for the Podman Desktop AI Lab extension’s sample applications, or recipes. There’s an excellent post that describes the AI Lab extension. In this workshop, we'll explore AI Lab Recipes further. We’ll use the RAG application as an example throughout. To follow along, clone the ai-lab-recipes repository locally. Also, if you don’t yet have Podman installed, head to podman.io.

There are several recipes to help developers quickly prototype new AI and large language model (LLM)-based applications. Each recipe includes the same main ingredients: models, model servers, and AI interfaces. These are combined in various ways, packaged as container images, and can be run as pods with Podman. The recipes are grouped into different categories (food groups) based on the AI functions. The current recipe groups are audio, computer vision, multimodal, and natural language processing. 

**Repository**: [https://github.com/containers/ai-lab-recipes](https://github.com/containers/ai-lab-recipes)


Now that we have understood all the major concepts, let's begin with the workshop! 🎆

