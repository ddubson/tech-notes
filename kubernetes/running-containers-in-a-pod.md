# Running Containers in Pods

## Pod Definition

* Done either via JSON or YAML concept
* Set the desired state of the pod via configuration
* e.g. nginx yaml pod definition \(nginx.yaml\)

```Yaml
apiVersion: v1
kind: Pod
metadata:
    name: nginx
spec:
    containers:
        - name: nginx
          image: nginx:1.7.9
          ports:
            - containerPort: 80
```

Pod Commands

```
# No pods initially
kubectl get pods

# Create pod with yml config
kubectl create -f ./nginx.yaml

# Pods are now running
kubectl get pods

# Information about pod
kubectl describe pod nginx

# Create a busybox pod
kubectl run busybox —image=busybox —restart=Never —tty -i —generator=run-pod/v1

# Deletes a pod
kubectl delete pod nginx

# Port forward to 80 on nginx
kubectl port-forward nginx :80
```

## Tags, Labels, Selectors

* Create new nginx pod yamL with “labels metadata”

```
apiVersion: v1
kind: Pod
metadata:
    name: nginx
  labels:
        app: nginx
spec:
    containers:
        - name: nginx
          image: nginx:1.7.9
          ports:
            - containerPort: 80
```

* `kubectl get pods -l app=nginx` -&gt; get all pods that are labeled with k-v app=nginx
* `kubectl get pods -l app=nginx` -&gt; description for ‘nginx’ pod

## Deployment State

* Create a new nginx config: `nginx-deployment-prod.yaml`

```
apiVersion: extensions/v1beta1
kind: Deployment
metadata:
    name: nginx-deployment-prod
spec:
    replicas: 1
    template:
        metadata:
              labels:
                app: nginx-deployment-prod
        spec:
            containers:
                - name: nginx-deployment-prod
                    image: nginx:1.7.9
                    ports:
                      - containerPort: 80
```

* `kubectl create -f nginx-deployment-prod.yaml`
* `kubectl get deployments` -&gt; lists all deployments

* Create a new deployment for dev:

```
apiVersion: extensions/v1beta1
kind: Deployment
metadata:
    name: nginx-deployment-dev
spec:
    replicas: 1
    template:
        metadata:
              labels:
                app: nginx-deployment-dev
        spec:
            containers:
                - name: nginx-deployment-dev
                    image: nginx:1.7.9
                    ports:
                     - containerPort: 80
```

* By using a deployment type, we can update pods by applying an updated deployment.
* Upgrade nginx from 1.7.9 to 1.8.0

```yaml
apiVersion: extensions/v1beta1
kind: Deployment
metadata:
    name: nginx-deployment-dev
spec:
    replicas: 1
    template:
        metadata:
              labels:
                app: nginx-deployment-dev
        spec:
            containers:
                - name: nginx-deployment-dev
                    image: nginx:1.8
                    ports:
                - containerPort: 80
```

* `kubectl apply -f nginx-deployment-dev-update.yaml` -&gt; applies changes from the new configuration

## Multi-Pod \(Container\) Replication Controller

* Multiple containers in a pod - replication controller
* Edit nginx-multi-label.yaml

```
apiVersion: v1
kind: ReplicationController
metadata:
    name: nginx-www
spec:
    replicas: 3
    selector:
        app: nginx
    template:
        metadata:
            name: nginx
            labels:
                app: nginx
        spec:
            containers:
                - name: nginx
                  image: nginx
                  ports:
                     - containerPort: 80
```

* 1 pod of each type on each minion \(given 3 minions\)

```
kubectl create -f nginx-multi-label.yaml
kubectl create describe replication controller
kubectl get services
```

* If a pod is deleted, replication controller spins up another to have the same consistent state \(3 pods\)
* \`kubectl delete replicationcontroller nginx-www\` - delete rep controller by name

## Create/Deploy Service Definitions

* Creating a service

```yml
apiVersion: v1
kind: Service
metadata:
    name: nginx-service
spec:
    ports:
        - port: 8000
          targetPort: 80
          protocol: TCP
    selector:
        app: nginx
```

Run 

```
kubectl create -f nginx-service.yml
kubectl get services
```

![](/assets/kube-1.png)Now all the minions are round-robin load balanced with a single ip \(CLUSTERIP\)

-&gt; Run \`kubectl describe service nginx-service\`![](/assets/kube-2.png)

## Temporary Pods via command line

* How to create a temporary pod without a yml file:

```
kubectl run mysample --image=latest123/apache # creates a deployment
kubectl delete deployment mysample # delete deployment created
kubectl run myreplicas —image=latest123/apache —replicas=2 —labels=app=myapache,version=1.0 # create a pod with replica factor of 2
```

### Interacting with Pod containers

* \`kubectl exec myapache date\` -&gt; run ‘date’ command in pod \`myapache\`

* \`kubectl exec myapache -i -t — /bin/bash\` -&gt; run bash in the single container in the pod \(otherwise specify \`-c ContID\`\)



