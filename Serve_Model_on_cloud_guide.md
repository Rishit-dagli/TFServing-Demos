# Serve Model on Cloud with Kubernetes and TF Model server

Fortunately, distributed workloads are becoming easier to manage, thanks to Kubernetes. Kubernetes is a mature, production ready platform 
that gives developers a simple API to deploy programs to a cluster of machines as if they were a single piece of hardware. Using Kubernetes
, computational resources can be added or removed as desired, and the same cluster can be used to both train and serve ML models.

## What will we do

This guide will describe how to train and serve a TensorFlow model, and then how to deploy a web interface to allow users to interact 
with the model over the public internet. You will build a classic handwritten digit recognizer using the MNIST dataset.

We will use the following workflow to do so:

![](images/kubeflow_workflow.png)

We will discretely follow these steps:

- Build a training image using your TensorFlow model code and Kubeflow's Fairing.
- Set up and run a distributed training job using TFJob.
- **Serve the resulting model using TensorFlow Serving.**
- Deploy a web app that uses the model

## What you need

- An active GCP project
- Basic TF Model server knowledge
- Basic model building knowledge in Keras
