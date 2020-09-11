# LAB: Google Cloud Fundamentals: Getting Started with Compute Engine
---
## Objectives:
---


*In this lab, you learn how to perform the following tasks:*

- Create a Compute Engine virtual machine using the Google Cloud Platform (GCP) Console.

- Create a Compute Engine virtual machine using the gcloud command-line interface.

- Connect between the two instances

---
## STEPS TO CREATE A VIRTUAL MACHINE USING THE GCP CONSOLE
---


1. Create a Compute Engine virtual machine using the Google Cloud Platform (GCP) console.

	`gcloud compute instances create my-vm-1 --machine-type "n1-standard-1" --image-project "debian-cloud" --image "debian-9-stretch"