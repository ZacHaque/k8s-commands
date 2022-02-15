# Imperetive command :

For a quick a deployment -

`kubectl run blue --image=nginx --replicas=6`

Scaling up/down -

`kubectl scale deploy/blue --replicas=4`

Changing Image -

`kubectl set image deployment/blue blue=nginx:1.16.1 --record`

Check on rollout history -

`k rollout history deploy/blue`

Undo a rollout to previous version -

`k rollout undo deploy/blue`

Undo a rollout to previous specific version -

`k rollout undo deploy/blue --to-revision=1`

Create NodePort Service -

`k create service nodeport testing-1 --tcp=8090:80 --node-port=30020`

Use as suffix to get yaml(applies to most command above) -

`--dry-run -o yaml > myfile.yaml`

To get all the pods wich a label - eg : where there is a label run: red

`k get po --selector run=red`

Command to remember -

```
k run myserver --image=nginx --dry-run -o yaml --restart=Always --port=90 -r=6 -l=family=haq --limits='cpu=100m,memory=256Mi' --requests='cpu=10m,memory=128Mi' --env=COL=red -n=test
```

Create POD along with the service -

```
kubectl run nginx --image=nginx --restart=Never --port=80 --expose --dry-run -o yaml
```

Test connection

```
kubectl run tester --restart=Never --image=busybox --rm -it -- wget -O- http://nginx:80 --timeout 2
```

Other handy command to generate yaml -

```
k run nginx --image=nginx   (deployment)
k run nginx --image=nginx --restart=Never   (pod)
k run nginx --image=nginx --restart=OnFailure   (job)  
k run nginx --image=nginx  --restart=OnFailure --schedule="* * * * *" (cronJob)

k run nginx --image=nginx --restart=Never --port=80 --namespace=myname --command --serviceaccount=mysa1 --env=HOSTNAME=local --labels=bu=finance,env=dev  --requests='cpu=100m,memory=256Mi' --limits='cpu=200m,memory=512Mi' --dry-run -o yaml -- /bin/sh -c 'echo hello world'

k run frontend --replicas=2 --labels=run=load-balancer-example --image=busybox  --port=8080
k expose deployment frontend --type=NodePort --name=frontend-service --port=6262 --target-port=8080
k set serviceaccount deployment frontend myuser
k create service clusterip my-cs --tcp=5678:8080 --dry-run -o yaml
k create service nodeport testing-1 --tcp=8090:80 --node-port=30020
```

Port forwarding for local running kube cluster

```yaml
kubectl port-forward -n argocd svc/argocd-server 8080:443
```

## Referrence-

https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands

https://www.youtube.com/watch?v=rnemKrveZks&feature=youtu.be
