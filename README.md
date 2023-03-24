<h1 align="center">Greenmail Helm Chart</h1>

<br>

<p align="center">
  The <code>Greenmail Helm Chart</code> is the standard way to deploy <a href="https://greenmail-mail-test.github.io/greenmail/">Greenmail</a> on <a href="https://kubernetes.io/">Kubernetes</a> with <a href="https://helm.sh/">Helm</a>.
  <br>
  Originally created in 2023, it has since helped create deployments of Greenmail on Kubernetes.
</p>

<p align="center">
  <a href="https://github.com/tgeci/greenmail-helm/releases">
    <img alt="Downloads" src="https://img.shields.io/github/downloads/tgeci/greenmail-helm/total">
  </a>
    <a href="https://github.com/tgeci/greenmail-helm/blob/main/LICENSE">
    <img alt="License" src="https://img.shields.io/github/license/tgeci/greenmail-helm">
  </a>
</p>

<br>

## History

This project is independent from the official chart found in the `greenmail-mail-test/greenmail` GitHub repository. Originally created in 2023, it has since helped to create deployments of Greenmail on Kubernetes.

Greenmail allows developers to test email-based applications, services or systems without access to a live mail server. Developers can send, receive, and verify emails by embedding GreenMail in a unit test or running it as a standalone container. GreenMail acts as a virtual (mocking/sandbox) mail server and supports common mail protocols SMTP, IMAP and POP3.

## Quickstart Guide

> click the `▶` symbol to expand
<details>
<summary><code>Prepare your environment</code></summary>

- Kubernetes `1.16+`
- Helm `3.0+` ([installing helm](https://helm.sh/docs/intro/install/))

> 🟦 __Tip__ 🟦
>
> To deploy the `Greenmail Helm Chart` you will need a Kubernetes cluster.
> <br>
> The following table lists some popular Kubernetes distributions by platform.
>
> Platform | Kubernetes Distribution
> --- | ---
> Local Machine | [k3d](https://k3d.io/)
> Local Machine | [kind](https://kind.sigs.k8s.io/)
> Local Machine | [minikube](https://minikube.sigs.k8s.io/)
> Amazon Web Services | [Amazon Elastic Kubernetes Service (EKS)](https://aws.amazon.com/eks/)
> Microsoft Azure | [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/en-au/services/kubernetes-service/)
> Google Cloud | [Google Kubernetes Engine (GKE)](https://cloud.google.com/kubernetes-engine)
> Alibaba Cloud | [Alibaba Cloud Container Service for Kubernetes (ACK)](https://www.alibabacloud.com/product/kubernetes)
> IBM Cloud | [IBM Cloud Kubernetes Service (IKS)](https://www.ibm.com/cloud/kubernetes-service)
  
</details>

<details>
<summary><code>Installation</code></summary>

The following commands will add our repository to your helm:

```shell
## add this helm repository
helm repo add greenmail https://tgeci.github.io/greenmail-helm/
## update your helm repo cache
helm repo update
  
## To install the chart with the release name `greenmail`
helm install greenmail tgeci/greenmail-helm
```  
</details>

<details>
<summary><code>Uninstallation</code></summary>

```shell
## to uninstall the `greenmail` release:
helm uninstall greenmail
```
</details>


## Helm Values

The following is a summary of the __helm values__ provided by this chart (see full list in [`values.yaml`](https://github.com/tgeci/greenmail-helm/blob/main/greenmail/values.yaml) file).

> click the `▶` symbol to expand
<details>
<summary><code>values</code></summary>

| Parameter | Description | Default |
| --- | --- | --- |
| `image.repository` | Greenmail container image repository | `"greenmail/standalone:2.0.0"` |
| `image.pullPolicy` | Greenmail container image pull policy | `"IfNotPresent"` |
| `image.tag` | Greenmail container image tag | `"2.0.0"` |
| `replicaCount` | Number of Greenmail replicas to deploy | `1` |
| `smtpPort` | Greenmail SMTP port | `3025` |
| `imapPort` | Greenmail IMAP port | `3143` |
| `ssl.enabled` | Enable SSL for Greenmail | `false` |
| `resources` | Resource requests and limits for the Greenmail container | `{}` |
| `nodeSelector` | Node labels for pod assignment | `{}` |
| `tolerations` | Tolerations for pod assignment | `[]` |
| `affinity` | Affinity for pod assignment | `{}` |

</details>
