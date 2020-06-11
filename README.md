# k8s

## Pod Design
### Multicontainer Pods
* https://medium.com/bb-tutorials-and-thoughts/understanding-multi-container-pods-12f5780f3956
## Services
* https://medium.com/swlh/kubernetes-services-simply-visually-explained-2d84e58d70e5

## CKAD Practice Resources

## CKA Practice Resources

###  Create Volume Claim:
This is test volume
DO this
do that

![](https://solitusa.com/api?repo=CKAD-exercises/pod_design&empty)
# Pod design (20%)

## Labels and annotations
kubernetes.io > Documentation > Concepts > Overview > [Labels and Selectors](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/#label-selectors)

### Create 3 pods with names nginx1,nginx2,nginx3. All of them should have the label app=v1

<details><summary>show</summary>
<p>

```bash
kubectl run nginx1 --image=nginx --restart=Never --labels=app=v1
kubectl run nginx2 --image=nginx --restart=Never --labels=app=v1
kubectl run nginx3 --image=nginx --restart=Never --labels=app=v1
```

</p>
</details>

### Show all labels of the pods

<details><summary>show</summary>
<p>

```bash
kubectl get po --show-labels
```

</p>
</details>
