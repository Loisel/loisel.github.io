---
title: "Heureka"
date: 2022-12-20T15:11:59+01:00
startdate: 2022-09-20
draft: false
description: "Web interface for the energy system model Calliope"
image: "heureka_logo.png"
languages: "Python, JavaScript"
technologies: "Django, Celery, jQuery, Docker, Ansible, Terraform"
---

<img class="img-fluid rounded float-start me-3" src="heureka_logo.png">

The client supports a contractor for wind parks to set up an optimization tool
for the layout of production and storage capacities for different energy carriers.
For the optimization the client chose [Calliope](https://calliope.readthedocs.io/en/stable/),
a multi-scale energy systems modelling framework.


### Task
Create a ready-to-use web interface for the client to encapsulate the rich
Calliope functionality. The user should be able to set up a valid model and perform the optimization.
Results are visualized by a range of plots.

### Architecture
All services reside in Docker containers. In the backend I use Django, for the frontend
we keep things simple and rely on Javascript/jQuery to provide a basic level of interactivity.
The instance running the optimization 
problem has it's own container. For the management of the asynchronous tasks we apply Celery, 
the parameters for the tasks are delivered via a rabbitmq broker.
Automated E2E tests were designed with selenium and run in a headless chromium container in github actions.
Deployment is automated with Ansible. For the cloud setup we use Terraform.


