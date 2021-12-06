![TMC Policy slide]

One of the key reason Kubernetes has grown so popular is that it provides application development teams a single API to drive infrastructure according to their application requirements and does so in a simplified manner. Application development teams do not need to understand the nuanced details of the underlying backend infrastructure as Kubernetes focuses on the needs of the application while the integrations focus on the infrastructure team's requirements to provide to them and it does so consistently even if it is a public cloud, private cloud, or on-premises datacenter. If they need a storage volume provisioned or a load balancer provisioned, it's a simple Kubernetes API call away. Kubernetes drives the backend infrastructure based on the API call request and provisions/changes compute, storage and network accordingly.
---
While this Kubernetes capability makes the day to day lot more streamlined and simplified for application development teams, it also gives Development teams unbound access to the Infrastructure. They can drive as many storage volumes, compute instances or Load Balancers needed, drive external traffic to applications/databases within the security perimeter of an Organization, or expose internal data. They can deploy containers from the internet with vulnerabilities etc. As such, running Kubernetes platform with appropriate polices that implement security best practices is imperative.

1. How do you ensure role based access control is applied consistently?
2. How do you control where container images come from and are deployed to your clusters?
3. How do you ensure network traffic is limited appropriately between pods?
4. How do you allow pods to have the correct level of permissions to the underlying host to function but not more?
5. How can you allow for multi-tenancy within a cluster, allowing teams to consume their share of resources?

Tanzu Mission Control provides out of the box policies that can be applied in a blanket mode to Kubernetes Clusters across multiple cloud and on-prem environments. Tanzu Mission Control also provides a way to build custom polices based on an Organizations unique requirements.