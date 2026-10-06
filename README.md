<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Recover an Azure Container App Outage

**Project Link:** [View Project](https://nextwork.ai/projects/8fce6c1c-bf35-44dd-ae7e-27040acc3c20)

**Author:** Ahens4055  
**Email:** ahens.str.jbr@gmail.com

---

![Image](https://nextwork.ai/sparkling_orange_playful_grapefruit/uploads/8fce6c1c-bf35-44dd-ae7e-27040acc3c20_1wrplsuz)

## Launching an Azure Container Apps Incident Lab

### Building production-style troubleshooting skills

I'm running an Azure support incident lab to practice navigating the Azure Container Apps service and learn how to resolve issues when it goes down.

## Preparing an Azure Operations Console

### Setting up an isolated Azure CLI environment

In this step, I'm setting up Azure account through portal and isolating my environment using a containerized Azure CLI, authenticating my subscription, and registering the Microsoft.App provider so that I can establish a clean, production-ready operations console for managing Azure Container Apps without affecting my host machine.

![Image](https://nextwork.ai/sparkling_orange_playful_grapefruit/uploads/8fce6c1c-bf35-44dd-ae7e-27040acc3c20_h0hddez2)

### Verifying subscription access and provider readiness

I confirmed the console by checking that the active Azure CLI container is running and authenticated to the intended subscription, and observing that the Microsoft.App provider registration state is Registered.

## Launching a Healthy Public Container App

### Creating a scale-to-zero public service baseline

In this step, I'm setting up a dedicated Azure resource group, provisioning a Container Apps environment, and deploying a quickstart workload with a public scale-to-zero endpoint so that I can establish a healthy service baseline for the incident drill.

![Image](https://nextwork.ai/sparkling_orange_playful_grapefruit/uploads/8fce6c1c-bf35-44dd-ae7e-27040acc3c20_clhseant)

## Reproducing an Ingress Routing Outage

### Introducing an intentional target-port failure

In this step, I'm capturing the healthy ingress baseline, changing the live target port from 80 to 81, and requesting the public endpoint so that I can introduce a configuration fault and experience a real ingress outage.

![Image](https://nextwork.ai/sparkling_orange_playful_grapefruit/uploads/8fce6c1c-bf35-44dd-ae7e-27040acc3c20_2or4bw2y)

## Isolating the Target-Port Mismatch

### Investigating with logs, live configuration, and diagnostics

In this step, I'm reviewing real-time system logs, comparing the live ingress target port with the image's listening port, and running the Azure portal ingress detector so that I can investigate the port mismatch fault and diagnose the root cause of the outage.

### Comparing ingress routing with the container listening port

I confirmed the mismatch by comparing the live ingress targetPort set to 81 with the quickstart image ([mcr.microsoft.com/k8se/quickstart:latest](https://mcr.microsoft.com/k8se/quickstart:latest)) which listens on port 80, proving that traffic was sent to a port with no application listener.

![Image](https://nextwork.ai/sparkling_orange_playful_grapefruit/uploads/8fce6c1c-bf35-44dd-ae7e-27040acc3c20_seq4mcln)

## Restoring Service and Documenting the Incident

### Correcting ingress and validating recovery

In this step, I'm recovering the service by restoring the ingress target port to 80, verifying the repaired configuration and public endpoint, and creating an incident report from the evidence collected so that I can successfully resolve the outage and document the resolution.

### Connecting root cause, remediation, and recovery evidence

I connected the outage to the port mismatch where external ingress was routed to port 81 while the container listened on port 80, and I verified recovery by restoring the target port back to 80 and confirming the public endpoint returned a healthy response.

## Protecting Live Traffic with Single-Revision Mode

![Image](https://nextwork.ai/sparkling_orange_playful_grapefruit/uploads/8fce6c1c-bf35-44dd-ae7e-27040acc3c20_9sldbdaq)

### Learning why a failed image revision did not disrupt users

In this project extension, I learned that single revision mode maintains a continuous active state while applying changes, which ensures that configuration updates replace the active deployment in-place, allowing us to directly experience, diagnose, and troubleshoot live runtime issues like port mismatches.

## Reflecting on Azure Incident Response Skills

### Tools and concepts applied

The key tools I used include the Azure CLI, Docker, and the Azure Portal. Key concepts I learnt include diagnosing ingress port mismatches, managing container app environments and revisions, inspecting container listening ports, and executing service recovery and incident documentation.

### Project duration and challenge reflection

This project took me approximately 60-80 minutes to complete. The most challenging part was diagnosing the port mismatch by comparing the live ingress configuration against the container image's default listening port and handling CLI environment variables across multiple terminal sessions.

### Continuing the cloud operations learning journey

I did this project today to learn how to troubleshoot and resolve ingress outages in Azure Container Apps by diagnosing port mismatches, inspecting container configurations, and managing revisions. Another skill I want to learn is setting up secure virtual network (VNet) integration and custom domains for containerized workloads.

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/8fce6c1c-bf35-44dd-ae7e-27040acc3c20)*
