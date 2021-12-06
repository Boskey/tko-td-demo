![Network-policy]

## Implement Network Policies

By default, Kubernetes provides an open, flat network which is often not desirable. Many applications, especially when we are running microservices, only need to communicate to a few other services. Network policies allow us to define some default network rules on Workspaces to control the flow of network traffic for the services communicating in and out of a cluster.
---

To view these policies:

- Click on **Network** tab within the policy assignments section.

---
- Click on **Workspaces** as network policies can only be applied to workspaces.

---
- Click **Create Network Policy** to view the wizard, reviewing the options in the Network policy dropdown.

**Note**: In order for network policies to be effective, the CNI deployed to your Kubernetes cluster must support network policies.
