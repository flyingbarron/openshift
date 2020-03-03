---

copyright:
  years: 2014, 2020
lastupdated: "2020-03-03"

keywords: openshift, roks, rhoks, rhos

subcollection: openshift

---

{:codeblock: .codeblock}
{:deprecated: .deprecated}
{:download: .download}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}
{:gif: data-image-type='gif'}
{:help: data-hd-content-type='help'}
{:important: .important}
{:new_window: target="_blank"}
{:note: .note}
{:pre: .pre}
{:preview: .preview}
{:screen: .screen}
{:shortdesc: .shortdesc}
{:support: data-reuse='support'}
{:table: .aria-labeledby="caption"}
{:tip: .tip}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}


# Moving your environment to Red Hat OpenShift on IBM Cloud
{: #strategy}

With {{site.data.keyword.openshiftlong}}, you can quickly and securely deploy container workloads for your apps in production. Learn more so that when you plan your cluster strategy, you optimize your setup to make the most of [Kubernetes](https://kubernetes.io/){: external} automated deploying, scaling, and orchestration management capabilities.
{:shortdesc}

## Moving your workloads to the {{site.data.keyword.cloud_notm}}
{: #cloud_workloads}

You have lots of reasons to move your workloads to {{site.data.keyword.cloud_notm}}: reducing total cost of ownership, increasing high availability for your apps in a secure and compliant environment, scaling up and down in respond to your user demand, and many more. Red Hat OpenShift on IBM Cloud combines container technology with open source tools, such as Kubernetes so that you can build a cloud-native app that can migrate across different cloud environments, avoiding vendor lock-in.
{:shortdesc}

But how do you get to the cloud? What are your options along the way? And how do you manage your workloads after you get there?

Use this page to learn some strategies for your Kubernetes deployments on Red Hat OpenShift on IBM Cloud. And always feel free to engage with our team on [Slack](https://ibm-cloud-success.slack.com){: external}.

Not on slack yet? [Request an invite!](https://cloud.ibm.com/kubernetes/slack){: external}
{: tip}

### Can I automate my infrastructure deployments?
{: #packaging}

If you want to run your app in multiple clusters, public and private environments, or even multiple cloud providers, you might wonder how you can make your deployment strategy work across these environments.

You can use the open source [Terraform](/docs/terraform?topic=terraform-getting-started#getting-started) tool to automate the provisioning of {{site.data.keyword.cloud_notm}} infrastructure, including Kubernetes clusters. Follow along with this tutorial to [plan, create, and update deployment environments](/docs/tutorials?topic=solution-tutorials-plan-create-update-deployments#plan-create-update-deployments). After you create a cluster, you can also set up the [Red Hat OpenShift on IBM Cloud cluster autoscaler](/docs/openshift?topic=openshift-ca) so that your worker pool scales up and down worker nodes in response to your workload's resource requests.</dd>

### What kind of apps can I run? Can I move existing apps, or do I need to develop new apps?
{: #app_types}

Your containerized app must be able to run on the supported operating system, Ubuntu 16.64, 18.64. You also want to consider the statefulness of your app. For more information about the kinds of apps that can run in Red Hat OpenShift on IBM Cloud, see [Planning app deployments](/docs/openshift?topic=openshift-plan_deploy#app_types).

If you already have an app, you can [migrate it to Red Hat OpenShift on IBM Cloud](/docs/openshift?topic=openshift-plan_deploy#migrate_containerize). If you want to develop a new app, check out the [guidelines for developing stateless, cloud-native apps](/docs/openshift?topic=openshift-plan_deploy#12factor)

### What knowledge and technical skills are good to have before I move my apps to Red Hat OpenShift on IBM Cloud?
{: #knowledge}

OpenShift is designed to provide capabilities to two main personas, the cluster admin and the app developer. Each persona uses different technical skills to successfully run and deploy apps to a cluster.
{: shortdesc}

**What are a cluster admin's main tasks and technical knowledge?** </br>
As a cluster admin, you are responsible to set up, operate, secure, and manage the {{site.data.keyword.cloud_notm}} infrastructure of your cluster. Typical tasks include:
- Size the cluster to provide enough capacity for your workloads.
- Design a cluster to meet the high availability, disaster recovery, and compliance standards of your company.
- Secure the cluster by setting up user permissions and limiting actions within the cluster to protect your compute resources, your network, and data.
- Plan and manage network communication between infrastructure components to ensure network security, segmentation, and compliance.
- Plan persistent storage options to meet data residency and data protection requirements.

The cluster admin persona must have a broad knowledge that includes compute, network, storage, security, and compliance. In a typical company, this knowledge is spread across multiple specialists, such as System Engineers, System Administrators, Network Engineers, Network Architects, IT Managers, or Security and Compliance Specialists. Consider assigning the cluster admin role to multiple people in your company so that you have the required knowledge to successfully operate your cluster.

**What are an app developer's main tasks and technical skills?** </br>
As a developer, you design, create, secure, deploy, test, run, and monitor cloud-native, containerized apps in an OpenShift cluster. To create and run these apps, you must be familiar with the concept of microservices, the [12-factor app](/docs/openshift?topic=openshift-plan_deploy#12factor) guidelines, [Docker and containerization principles](https://www.docker.com/), and available [OpenShift deployment options](/docs/openshift?topic=openshift-plan_deploy). If you want to deploy serverless apps, make yourself familiar with [Knative](/docs/containers?topic=containers-cs_network_planning).

OpenShift and Red Hat OpenShift on IBM Cloud provide multiple options for how to [expose an app and keep an app private](/docs/containers?topic=containers-cs_network_planning), [add persistent storage](/docs/openshift?topic=openshift-storage_planning), [integrate other services](/docs/openshift?topic=openshift-ibm-3rd-party-integrations), and how you can [secure your workloads and protect sensitive data](/docs/openshift?topic=openshift-security#container). Before you move your app to a cluster in Red Hat OpenShift on IBM Cloud, verify that you can run your app as a containerized app on the supported RHEL 7 operating system and that OpenShift and Red Hat OpenShift on IBM Cloud provide the capabilities that your workload needs.

**Do cluster administrators and developers interact with each other?** </br>
Yes. Cluster administrators and developers must interact frequently so that cluster administrators understand workload requirements to provide this capability in the cluster, and so that developers know about available limitations, integrations, and security principles that they must consider in their app development process.

## Sizing your OpenShift cluster to support your workload
{: #sizing}

Figuring out how many worker nodes you need in your cluster to support your workload is not an exact science. You might need to test different configurations and adapt. Good thing that you are using Red Hat OpenShift on IBM Cloud, where you can add and remove worker nodes in response to your workload demands.
{: shortdesc}

To get started on sizing your cluster, ask yourself the following questions.

### How many resources does my app require?
{: #sizing_resources}

First, let's begin with your existing or project workload usage.

1.  Calculate your workload's average CPU and memory usage. For example, you might view the Task Manager on a Windows machine, or run the `top` command on a Mac or Linux. You might also use a metrics service and run reports to calculate workload usage.
2.  Anticipate the number of requests that your workload must serve so that you can decide how many app replicas you want to handle the workload. For example, you might design an app instance to handle 1000 requests per minute and anticipate that your workload must serve 10000 requests per minute. If so, you might decide to make 12 app replicas, with 10 to handle the anticipated amount and an extra 2 for surge capacity.

### What else besides my app might use resources in the cluster?
{: #sizing_other}

Now let's add some other features that you might use.



1.  Consider whether your app pulls large or many images, which can take up local storage on the worker node.
2.  Decide whether you want to [integrate services](/docs/openshift?topic=openshift-supported_integrations#supported_integrations) into your cluster, such as [Helm](/docs/openshift?topic=openshift-helm#public_helm_install) or [Prometheus](https://github.com/coreos/prometheus-operator/tree/master/contrib/kube-prometheus){: external}. These integrated services and add-ons spin up pods that consume cluster resources.

### What type of availability do I want my workload to have?
{: #sizing_availability}

Don't forget that you want your workload to be up as much as possible!

1.  Plan out your strategy for [highly available clusters](/docs/openshift?topic=openshift-ha_clusters#ha_clusters), such as deciding between single or multizone clusters.
2.  Review [highly available deployments](/docs/openshift?topic=openshift-plan_deploy#highly_available_apps) to help decide how you can make your app available.

### How many worker nodes do I need to handle my workload?
{: #sizing_workers}

Now that you have a good idea of what your workload looks like, let's map the estimated usage onto your available cluster configurations.

1.  Estimate the max worker node capacity, which depends on what type of cluster you have. You don't want to max out worker node capacity in case a surge or other temporary event happens.
    *  **Single zone clusters**: Plan to have at least three worker nodes in your cluster. Further, you want one extra node's worth of CPU and memory capacity available within the cluster.
    *  **Multizone clusters**: Plan to have at least two worker nodes per zone, so six nodes across three zones in total. Additionally, plan for the total capacity of your cluster to be at least 150% of your total workload's required capacity, so that if one zone goes down, you have resources available to maintain the workload.
2.  Align the app size and worker node capacity with one of the [available worker node flavors](/docs/openshift?topic=openshift-planning_worker_nodes#planning_worker_nodes). To see available flavors in a zone, run `ibmcloud oc flavors --zone <zone>`.
    *   **Don't overload worker nodes**: To avoid your pods competing for CPU or running inefficiently, you must know what resources your apps require so that you can plan the number of worker nodes that you need. For example, if your apps require less resources than the resources that are available on the worker node, you can limit the number of pods that you deploy to one worker node. Keep your worker node at around 75% capacity to leave space for other pods that might need to be scheduled. If your apps require more resources than you have available on your worker node, use a different worker node flavor that can fulfill these requirements. You know that your worker nodes are overloaded when they frequently report back a status of `NotReady` or evict pods due to the lack of memory or other resources.
    *   **Larger vs. smaller worker node flavors**: Larger nodes can be more cost efficient than smaller nodes, particularly for workloads that are designed to gain efficiency when they process on a high-performance machine. However, if a large worker node goes down, you need to be sure that your cluster has enough capacity to gracefully reschedule all the workload pods onto other worker nodes in the cluster. Smaller worker can help you scale more gracefully.
    *   **Replicas of your app**: To determine the number of worker nodes that you want, you can also consider how many replicas of your app that you want to run. For example, if you know that your workload requires 32 CPU cores, and you plan to run 16 replicas of your app, each replica pod needs 2 CPU cores. If you want to run only one app pod per worker node, you can order an appropriate number of worker nodes for your cluster type to support this configuration.
3.  Run performance tests to continue refining the number of worker nodes you need in your cluster, with representative latency, scalability, data set, and workload requirements.
4.  For workloads that need to scale up and down in response to resource requests, set up the [horizontal pod autoscaler](/docs/openshift?topic=openshift-update_app#app_scaling) and [cluster worker pool autoscaler](/docs/openshift?topic=openshift-ca#ca).

<br />


## Structuring your OpenShift environment
{: #kube_env}

Your Red Hat OpenShift on IBM Cloud is linked to one IBM Cloud infrastructure portfolio only. Within your account, you can create clusters that are composed of a master and various worker nodes. IBM manages the master, and you can create a mix of worker pools that pool together individual machines of the same flavor, or memory and CPU specs. Within the cluster, you can further organize resources by using namespaces and labels. Choose the right mix of cluster, flavors, and organization strategies so that you can make sure that your teams and workloads get the resources that they need.
{:shortdesc}

### What type of cluster and flavors should I get?
{: #env_flavors}

**Types of clusters**: Decide whether you want a [single zone, multizone, or multiple cluster setup](/docs/openshift?topic=openshift-ha_clusters#ha_clusters). Multizone clusters are available in [all six worldwide {{site.data.keyword.cloud_notm}} metro regions](/docs/openshift?topic=openshift-regions-and-zones#zones). Also keep in mind that worker nodes vary by zone.

**Types of worker nodes**: In general, your intensive workloads are more suited to run on bare metal physical machines, whereas for cost-effective testing and development work, you might choose virtual machines on shared or dedicated hardware. With bare metal worker nodes, your cluster has a network speed of 10 Gbps and hyper-threaded cores that offer higher throughput. Virtual machines come with a network speed of 1 Gbps and regular cores that do not offer hyper-threading. [Check out the machine isolation and flavors that are available](/docs/openshift?topic=openshift-planning_worker_nodes#planning_worker_nodes).

### Do I use multiple clusters, or just add more workers to an existing cluster?
{: #env_multicluster}

The number of clusters that you create depends on your workload, company policies and regulations, and what you want to do with the computing resources. You can also review security information about this decision in [Container isolation and security](/docs/openshift?topic=openshift-security#container).

**Multiple clusters**: You need to set up [a global load balancer](/docs/openshift?topic=openshift-ha_clusters#multiple_clusters) and copy and apply the same configuration YAML files in each to balance workloads across the clusters. Therefore, multiple clusters are generally more complex to manage, but can help you achieve important goals such as the following.
*  Comply with security policies that require you to isolate workloads.
*  Test how your app runs in a different version of OpenShift or other cluster software such as Calico.
*  Create a cluster with your app in another region for higher performance for users in that geographical area.
*  Configure user access on the cluster-instance level instead of customizing and managing multiple RBAC policies to control access within a cluster at the namespace level.

**Fewer or single clusters**: Fewer clusters can help you to reduce operational effort and per-cluster costs for fixed resources. Instead of making more clusters, you can add worker pools for different flavors of computing resources available for the app and service components that you want to use. When you develop the app, the resources it uses are in the same zone, or otherwise closely connected in a multizone, so that you can make assumptions about latency, bandwidth, or correlated failures. However, it becomes even more important for you to organize your cluster by using namespaces, resource quotas, and labels.

### How can I set up my resources within the cluster?
{: #env_resources}

<dl>
<dt>Consider your worker node capacity.</dt>
  <dd>To get the most out of your worker node's performance, consider the following:
  <ul><li><strong>Keep up your core strength</strong>: Each machine has a certain number of cores. Depending on your app's workload, set a limit for the number of pods per core, such as 10.</li>
  <li><strong>Avoid node overload</strong>: Similarly, just because a node can contain more than 100 pods doesn't mean that you want it to. Depending on your app's workload, set a limit for the number of pods per node, such as 40.</li>
  <li><strong>Don't tap out your cluster bandwidth</strong>: Keep in mind that network bandwidth on scaling virtual machines is around 1000 Mbps. If you need hundreds of worker nodes in a cluster, split it up into multiple clusters with fewer nodes, or order bare metal nodes.</li>
  <li><strong>Sorting out your services</strong>: Plan out how many services that you need for your workload before you deploy. Networking and port forwarding rules are put into Iptables. If you anticipate a larger number of services, such as more than 5,000 services, split up the cluster into multiple clusters.</li></ul></dd>
<dt>Provision different types of machines for a mix of computing resources.</dt>
  <dd>Everyone likes choices, right? With Red Hat OpenShift on IBM Cloud, you have [a mix of flavors](/docs/openshift?topic=openshift-planning_worker_nodes#planning_worker_nodes) that you can deploy: from bare metal for intensive workloads to virtual machines for rapid scaling. Use labels or namespaces to organize deployments to your machines. When you create a deployment, limit it so that your app's pod deploys only on machines with the right mix of resources. For example, you might want to limit a database application to a bare metal machine with a significant amount of local disk storage like the `md1c.28x512.4x4tb`.</dd>
<dt>Set up multiple namespaces when you have multiple teams and projects that share the cluster.</dt>
  <dd><p>Namespaces are kind of like a cluster within the cluster. They are a way to divide up cluster resources by using [resource quotas ![External link icon](../icons/launch-glyph.svg "External link icon")](https://kubernetes.io/docs/concepts/policy/resource-quotas/) and [default limits ![External link icon](../icons/launch-glyph.svg "External link icon")](https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/memory-default-namespace/). When you make new namespaces, be sure to set up proper [RBAC policies](/docs/openshift?topic=openshift-users#rbac) to control access. For more information, see [Share a cluster with namespaces ![External link icon](../icons/launch-glyph.svg "External link icon")](https://kubernetes.io/docs/tasks/administer-cluster/namespaces/) in the Kubernetes documentation.</p>
  <p>If you have a small cluster, a couple dozen users, and resources that are similar (such as different versions of the same software), you probably don't need multiple namespaces. You can use labels instead.</p></dd>
<dt>Set resource quotas so that users in your cluster must use resource requests and limits</dt>
  <dd>To ensure that every team has the necessary resources to deploy services and run apps in the cluster, you must set up [resource quotas](https://kubernetes.io/docs/concepts/policy/resource-quotas/) for every namespace. Resource quotas determine the deployment constraints for a project, such as the number of Kubernetes resources that you can deploy, and the amount of CPU and memory that can be consumed by those resources. After you set a quota, users must include resource requests and limits in their deployments.</dd>
<dt>Organize your Kubernetes objects with labels</dt>
  <dd><p>To organize and select your Kubernetes resources such as `pods` or `nodes`, [use Kubernetes labels ![External link icon](../icons/launch-glyph.svg "External link icon")](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/). By default, Red Hat OpenShift on IBM Cloud applies some labels, including `arch`, `os`, `region`, `zone`, and `machine-type`.</p>
  <p>Example use cases for labels include [limiting network traffic to edge worker nodes](/docs/openshift?topic=openshift-edge), [deploying an app to a GPU machine](/docs/openshift?topic=openshift-deploy_app#gpu_app), and [restricting your app workloads![External link icon](../icons/launch-glyph.svg "External link icon")](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/) to run on worker nodes that meet certain flavor or SDS capabilities, such as bare metal worker nodes. To see what labels are already applied to a resource, use the <code>oc get</code> command with the <code>--show-labels</code> flag. For example:</p>
  <p><pre class="pre"><code>oc get node &lt;node_ID&gt; --show-labels</code></pre></p>
  To apply labels to worker nodes, [create your worker pool](/docs/openshift?topic=openshift-add_workers#add_pool) with labels or [update an existing worker pool](/docs/openshift?topic=openshift-add_workers#worker_pool_labels).</dd>
</dl>

### How can I keep my cluster in a supported state?
{: #updating_kube}

Make sure that your cluster runs a [supported OpenShift version](/docs/openshift?topic=openshift-openshift_versions) at all times. When a new OpenShift minor version is released, an older version is shortly deprecated after and then becomes unsupported. For more information, see [Updating the master](/docs/openshift?topic=openshift-update#master) and [worker nodes](/docs/openshift?topic=openshift-update#worker_node).




<br />


## Making your resources highly available
{: #kube_ha}

While no system is entirely failsafe, you can take steps to increase the high availability of your apps and services in Red Hat OpenShift on IBM Cloud.
{:shortdesc}

Review more information about making resources highly available.
* [Reduce potential points of failure](/docs/openshift?topic=openshift-ha#ha).
* [Create multizone clusters](/docs/openshift?topic=openshift-ha_clusters#ha_clusters).
* [Plan highly available deployments](/docs/openshift?topic=openshift-plan_deploy#highly_available_apps) that use features such as replica sets and pod anti-affinity across multizones.
* [Run containers that are based on images in a cloud-based public registry](/docs/openshift?topic=openshift-images).
* [Plan data storage](/docs/openshift?topic=openshift-storage_planning#persistent_storage_overview). Especially for multizone clusters, consider using a cloud service such as [{{site.data.keyword.cloudant_short_notm}}](/docs/Cloudant?topic=cloudant-getting-started-with-cloudant) or [{{site.data.keyword.cos_full_notm}}](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started).
* For multizone clusters, enable a [load balancer service](/docs/openshift?topic=openshift-loadbalancer#multi_zone_config) or the Ingress [multizone load balancer](/docs/openshift?topic=openshift-ingress#ingress) to expose your apps publicly.

