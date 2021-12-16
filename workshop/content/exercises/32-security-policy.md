![Security Policy]
## Implement Security Policies

Containers are the base unit of deployment that runs any application on Kubernetes. Containers are processes that run on a given Kubernetes Host, they can have access to the host file systems, networks, host namespaces, password files, listen to traffic on the host etc. An application running in a container can see host/system level objects. To prevent containers from doing so, Kubernetes has created Admission Controllers that check the provisioning of a pod based on a set of Pod Security Policies (PSPs). It is important to not let containers access host based resources unless necessary as doing so opens unnecessary potential attack vectors. By default, Kubernetes does not implement any pod security policies.
---
By default, Tanzu Mission Control implements security policies around running pods with root access, privileged mode, access to host networks, volumes etc.
---
../images/tmc_Security_Policy_None.png

To view these policies:

- Click on the **Security** tab within the policy assignments section and click on the **Clusters** view if you are still seeing **Workspaces**.
---
../images/tmc_Security_Policy_None.png

Let's add a Direct Security policy for your cluster group

- Select the cluster group with your username in it
- Click on **Create Security Policy** Button 

---
../images/tmc_Security_Policy_Strict_Wizard.png

- Select **Strict** from the dropdown for **security template **
- Give the Policy a name, e.g: strict
- Click the button **Create Policy**

This will create a strict security policy that will disable any container from running that requires privileged mode. 
---
tmc_Security_Policy_Create_NGINX_Container.png

- Go to the Powershell window,
```execute
kubectl create deployment nginx --image=nginx 
```
---
tmc_Security_Policy_NGINX_Container_Failed.png
- Notice the pods do get created because default PSP is disabled on this cluster.
```execute
kubectl get pods 
```