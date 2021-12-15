![Access Policy](/workshop/content/images/29-access-policy.png)
## Providing RBAC and Authentication to Development Teams

 Kubernetes API is very important as it has the capability of accessing and modifying infrastructure objects. Kubernetes has it's own Role based access to the Kubernetes API that determine which user has what level of access. However, by default Kubernetes does not provide any Identity backed Authentication. Tanzu Mission Control provides the capability to automate role based access control to the API authenticated by your Organizations Identity services. VMware Cloud Services can federate to your LDAP, Active Directory, or SAML instance. Tanzu Mission Control will map a user from your organization to a role within the Kubernetes cluster. This is the access policy and can be applied in a blanket mode across clusters at once.
---
/workshop/content/images/tmc_Access_Policy.png

- Click on **Policies** from the left hand navigation menu, click **Assignments** then click on the **Access** tab.

- You will see a list of Cluster Groups with various clusters in it on the left hand side and access policies on the right hand
----
/workshop/content/images/tmc_Access_Policy_ClusterGroup_CreateRolebinding.png

- Click on the cluster group created for you ( starting with your username) from the cluster groups list and expand it

- Click on the Direct Access Polices on the right and click the button **Create Role Binding**
---
/workshop/content/images/tmc_Access_Policy_Create_Policy.png

- Select the Kubernetes Role from the **Roles** dropdown

- A user from the organizations identity provider can be added with an email ID or an imported drop-down list.
---
/workshop/content/images/tmc_Access_Policy_Create_Policy.png

- Exit out of the wizard by clicking the **Cancel** button.
---
/workshop/content/images/tmc_Access_Policy_View_Rolebinding.png

- Notice the existing role binding given to your email ID
  
---

Tanzu Mission Control has three methods to applying policies that are applied in a hierarchy. The root of this hierarchy is the Organization in Tanzu Mission Control. Next are Cluster Groups and the individual clusters. Workspaces and Namespaces make up the Workspaces. A policy applied at any lower level is carried forward to all further levels. Hence you might see Inherited Policies. Direct Policies can be applied to any object/level as well. Direct policies supersede Inherited policies.

The access policies applied above to the Cluster Group will be applied to all the clusters that are added to this group later on as well so as you create new or attach existing clusters, they will automatically inherit the access control settings you have put in place.