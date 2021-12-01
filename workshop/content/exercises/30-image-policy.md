![TMC Image Policy](../images/tmc-image-policy.png)
## Implement Image Registry Policy

The best part about containers is they are ultra-portable. They can be layered like a cake to build brand new images. A container image from the internet can be taken and used to add a new binary to build something custom. That's the appeal of containers. However, this means application development teams can download images from anywhere on the Internet and build new images inheriting vulnerabilities.

There are multiple ways to implement policies that make sure container images that get deployed are safe:

- Implement Vulnerability Scanning in the container Registry that stores the container images, and prevents images with critical vulnerabilities from being deployed (Harbor)
- Implement Policies to not allow images from certain Image Registries (TMC)
- Policy that prevents container images with no digest from deploying (TMC)
- Stop container images with latest tag from deploying (TMC)
- Blacklist certain images/repos (TMC)

Tanzu Mission Control, part of the the Tanzu for Kubernetes Operations solution provides out of the box policies that can be applied to a fleet of clusters spread across multiple clouds.

Tanzu Mission control has Image based policies that can be applied to namespaces within a cluster. These policies can be applied fleet-wide across clusters and clouds by grouping namespaces together in a logical group called **Workspaces**.

- Assuming you are still in **Policies**, click on the **Image Registry** tab and then **Workspaces**

- Select the workspace `tko-demo`

- You will notice a Direct Image Registry Policy applied called `no-busybox`

- Expand the policy `no-busybox` and click **EDIT** then click the first **Rule**

You will notice this is a custom policy that blocks any container image that has the name `busybox` on it:


- An image registry policy can have multiple rules. Take a look at the other attributes of image registry policies that can be applied as a rule.

Let's validate that our image registry policy is working by trying to deploy the `busybox` image on the namespace `tko-image-policy` which is part of the cluster `gke-psp-demo`.

- Go to the **Workshop** tab so you can see the **Terminal**.

- Make sure the namespace `tko-image-policy` exists on the cluster
```execute
kubectl --kubeconfig=kubeconfig-gke-psp-demo.yaml get ns
```

- Create a deployment with the image `busybox` from Docker Hub
```execute
kubectl --kubeconfig=kubeconfig-gke-psp-demo.yaml create deployment busybox --image=busybox -n tko-image-policy
```

- Notice the deployment is stuck and wont progress because of the image rules:
```execute
kubectl --kubeconfig=kubeconfig-gke-psp-demo.yaml describe deployment busybox -n tko-image-policy
```
  Notice the deployment isn't creating any replicas.

- Delete the deployment
```execute
kubectl --kubeconfig=kubeconfig-gke-psp-demo.yaml delete deployment busybox -n tko-image-policy
```
