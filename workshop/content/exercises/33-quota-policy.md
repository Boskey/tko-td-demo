## Implement Quota Policies

Application development teams love Kubernetes cause they can request infrastructure resources like compute, network and storage for running their apps without having to deal with Operations team or raise a ticket to provision things. On the flip side, this means the teams managing the platform need to be aware of the capacity they have and implement any quota/restrictions on consumption. Tanzu Mission Control's Quota based policy allows you to do just that from an operations perspective.
---
tmc_Quota_Policies_Clustergroup.png

- Go to the tab with Tanzu Mission Control, click on **Policies** then **Assignments**

- Click on the tab **Quota**, select **Cluster** then click on **Cluster Group** with your username in it
---
tmc_Quota_Policies_Clustergroup.png

- Notice there is no Direct Quota Policy applied

- Click on the button **Create Quota Policy** 
---
tmc_Quota_Policies_Wizard.png

- Select a policy type **small** from the **Quota Policy** dropdown

- Give it a name called **tanzu-quota **

- Notice it has been assigned an quota to limit of 1 vCPU and 2 GB of memory per workload.

- Click the button create 
---
tmc_Quota_Policy_Custom_Large.png

- You can opt to create a custom policy if you don't want to use any of the pre-defined ones or you wish to implement more detailed policies on objects such as: CPU, memory, storage, or even limits on most Kubernetes objects within a namespace.

Once complete, exit out of the wizard.
