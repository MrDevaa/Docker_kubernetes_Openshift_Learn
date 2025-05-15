# 📘 Glossary: Managing Applications with Kubernetes

Un glossaire des principaux termes liés à la gestion d'applications avec Kubernetes :

| **Term**                        | **Definition** |
|----------------------------------|----------------|
| **Cluster Autoscaler (CA)**      | An API resource that autoscales the cluster itself, increasing and decreasing the number of available nodes that pods can run on. |
| **Config Map**                   | An API object used to store non-confidential data in key-value pairs. Pods can consume ConfigMaps as environment variables, command-line arguments, or as configuration files in a volume. |
| **Horizontal Pod Autoscaler (HPA)** | An API resource that automatically scales the number of Pod replicas based on targeted CPU utilization or custom metric targets. |
| **Linguistic Analysis**          | Detects the tone in a given text. |
| **IBM Cloud Catalog**            | Provides various Services that range from visual recognition to natural language processing and creating chatbots. |
| **Persistent Volume (PV)**       | An API object that represents a piece of storage in the cluster. Available as a general, pluggable resource that persists beyond the lifecycle of any individual Pod. |
| **Persistent Volume Claim (PVC)**| Claims storage resources defined in a PersistentVolume so that it can be mounted as a volume in a container. |
| **Rolling Updates**              | Provide a way to roll out application changes in an automated and controlled fashion throughout your pods. Rolling updates work with pod templates such as deployments. Rolling updates allow for rollback if something goes wrong. |
| **Secrets**                      | Stores sensitive information, such as passwords, OAuth tokens, and ssh keys. |
| **Service Binding**              | The process needed to consume external Services or backing Services, including REST APIs, databases, and event buses in your applications. |
| **Tone Analyzer Service**        | Used for explaining service binding. This IBM Cloud Service uses linguistic analysis to detect tone in a given text. |
| **Vertical Pod Autoscaler (VPA)**| An API resource that adds resources to an existing machine. A VPA lets you scale a service vertically within a cluster. |
| **Volume**                       | A directory containing data, accessible to multiple containers in a Pod. |
| **Volume Mount**                 | Mounting of the declared volume into a container in the same Pod. |
| **Volume Plugin**                | Enables integration of storage within a Pod. |

---

🛠️ **Astuce :** Ces concepts sont fondamentaux pour concevoir des applications résilientes, évolutives et sécurisées dans un environnement Kubernetes.
