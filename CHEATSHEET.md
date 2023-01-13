## Pod Management

- `kubectl get pods` - list all pods in the current namespace
- `kubectl describe pod <pod-name>` - show detailed information about a specific pod
- `kubectl logs <pod-name>` - show the logs of a specific pod
- `kubectl exec -it <pod-name> <command>` - run a command in a specific pod
- `kubectl port-forward <pod-name> <local-port>:<remote-port>` - forward a local port to a specific pod
- `kubectl cp <file-path> <pod-name>:<destination-path>` - copy a file to a specific pod
- `kubectl label <resource-type> <resource-name> <label-key>=<label-value>` - add a label to a specific resource
- `kubectl get pods --all-namespaces` - list pods across all namespaces
- `kubectl get pods --watch` - list pods and stream updates to the output
- `kubectl get pods -l <label-key>` - list pods with a specific label
- `kubectl run <deployment-name> --image=<image-name> --port=<port-number>` - create and run a new deployment using the specified image and port
- `kubectl get pods -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}'` - list the names of all pods in jsonpath format
- `kubectl get pods -o jsonpath='{.items[*].status.phase}'` - list the status of all pods in jsonpath format
- `kubectl get pods -o jsonpath='{.items[*].spec.containers[*].name}'` - list the container names of all pods in jsonpath format
- `kubectl get pods -o jsonpath='{.items[*].spec.containers[*].image}'` - list the container images of all pods in jsonpath format
- `kubectl get pods --sort-by='.status.containerStatuses[0].restartCount'` - list all pods sorted by the number of times their main container has been restarted
- `kubectl get pods --sort-by='.status.startTime'` - list all pods sorted by start time
- `kubectl get pods --sort-by='.status.phase'` - list all pods sorted by status phase
- `kubectl get pods -o jsonpath='{.items[*].metadata.labels}'` - list all the labels of pods in jsonpath format
- `kubectl get pods -o jsonpath='{.items[*].metadata.annotations}'` - list all the annotations of pods in jsonpath format

## Service Management

- `kubectl get services` - list all services in the current namespace
- `kubectl describe service <service-name>` - show detailed information about a specific service
- `kubectl expose deployment <deployment-name> --type=<service-type> --port=<port-number> --name=<service-name>` - create a new service for a deployment
- `kubectl get services --all-namespaces` - list services across all namespaces
- `kubectl describe endpoints <endpoints-name>` - show detailed information about a specific endpoints
- `kubectl get services -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}'` - list the names of all services in jsonpath format
- `kubectl get services -o jsonpath='{.items[*].spec.ports[*].name}'` - list the ports name of all services in jsonpath foat
- `kubectl get services -o jsonpath='{.items[*].spec.ports[*].port}'` - list the ports number of all services in jsonpath format

## Deployment Management

- `kubectl get deployments` - list all deployments in the current namespace
- `kubectl describe deployment <deployment-name>` - show detailed information about a specific deployment
- `kubectl scale deployment <deployment-name> --replicas=<number>` - scale the number of replicas in a deployment
- `kubectl rolling-update <deployment-name> --image=<new-image-name>` - perform a rolling update to a deployment, replacing the current image with the specified new image
- `kubectl set image deployment <deployment-name> <container-name>=<new-image-name>` - update the image of a specific coainer in a deployment
- `kubectl create -f <yaml-file> --record` - create resources from a YAML file and create a rollback revision
- `kubectl rollout undo deployment <deployment-name>` - undo the last rollout of a deployment
- `kubectl set resources deployment <deployment-name> -c <container-name> --limits=cpu=200m,memory=512Mi` - set resource limits for a specific container in a deployment
- `kubectl get deployments --all-namespaces` - list deployments across all namespaces
- `kubectl get deployments --sort-by=.metadata.name` - list all deployments sorted by name

## Node Management

- `kubectl get nodes` - list all nodes in the cluster
- `kubectl describe node <node-name>` - show detailed information about a specific node
- `kubectl cordon <node-name>` - mark a node as unschedulable
- `kubectl uncordon <node-name>` - mark a node as schedulable
- `kubectl drain <node-name> --force --ignore-daemonsets` - Drain a node in the cluster, which will evicts the pods running on that node, and marks it unschedulable.
- `kubectl get nodes -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}'` - list the names of all nodes in jsonpath format
- `kubectl get nodes -o jsonpath='{.items[*].status.conditions[*].type}'` - list the conditions of all nodes in jsonpath format

## Namespace Management

- `kubectl get namespace` - list all namespaces
- `kubectl create namespace <namespace-name>` - create a new namespace
- `kubectl config set-context --current --namespace=<namespace-name>` - set the current namespace for kubectl
- `kubectl config view` - show the current kubectl configuration
- `kubectl get pods --selector=<label-key>=<label-value>` - list all pods with a specific label-value

## Miscellaneous

- `kubectl version` - show the version of kubectl and the connected Kubernetes cluster
- `kubectl help` - show the list of available kubectl commands and their usage
- `kubectl api-resources` - list all the resources that are available through Kubernetes API
- `kubectl config view` - show the current kubectl configuration
- `kubectl config set-cluster <cluster-name> --server=<cluster-url>` - set the cluster for kubectl to use
- `kubectl get events` - list all events in the current namespace
- `kubectl get events --sort-by=.lastTimestamp` - list all events sorted by timestamp
- `kubectl get events --field-selector=involvedObject.kind=Pod` - list all events related to pods
- `kubectl get events -w` - list all events and stream updates to the output
- `kubectl get events --all-namespaces` - list all events across all namespaces
