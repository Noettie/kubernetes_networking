Calico, from network software provider Tigera, is a third-party plugin for Kubernetes geared to make full network connectivity more flexible and easier. Out of the box, Kubernetes provides the NetworkPolicy API for managing network policies within the cluster. The problem many Kubernetes admins find (especially those new to the technology) is that network can quickly become a rather complicated mess of YAML configurations, where you must configure traffic ingress and egress properly, or communication between Kubernetes objects (such as pods and containers) can be difficult.

That’s where the likes of Calico come into play. Because not every Kubernetes network plugin supports NetworkPolicy API, it’s important that you select a plugin that will take care of your needs. For example, the most popular Kubernetes network plugin is Flannel, which cannot configure network policies. With Calico, you can significantly enhance the Kubernetes networking configuration.

Take, for instance, the feature limitations found in the default NetworkPolicy, which are:

Policies are limited to a single environment and are applied only to pods marked with labels.
You can only apply rules to pods, environments, or subnets.
Rules can only contain protocols, numerical ports, or named ports.
When you add the Calico plugin, the features are extended as such:

Policies can be applied to pods, containers, virtual machines, or interfaces.
Rules can contain a specific action (such as restriction, permission, or logging).
Rules can contain ports, port ranges, protocols, HTTP/ICMP attributes, IPs, subnets, or selectors for nodes (such as hosts or environments).
Traffic flow can be controlled via DNAT settings and policies.
Calico also supports multiple data planes, which allows you to choose the technology that best suits the needs of your project (including the pure Linux eBPF data plane). Other features include:

Highly performant.
Massive scalability.
Interoperability with current non-K8s workloads.
Full Kubernetes network policy support.
Very active development community.
To make Calico even more appealing, it’s available for use on all popular cloud platforms, such as Amazon Web Services, Microsoft  Azure, the Google Cloud Platform, IBM, Red Hat OpenShift and SUSE’s Rancher.

Or, if you prefer, you can deploy Calico on bare metal in your data center.

Let’s walk through the process of installing Calico on a small Kubernetes cluster. We’ll demonstrate on a cluster running on instances of Ubuntu Server 20.04, but the process should be the same, regardless of your platform. So long as you have access to kubectl, you should be good to go.

The first method will assume you already have your Kubernetes cluster up and running, while the second method starts on a bare-metal Ubuntu Server instance.
