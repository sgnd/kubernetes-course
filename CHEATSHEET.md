
# Kubernetes Cheatsheet — Practical kubectl commands & tips

This cheatsheet groups commonly used `kubectl` commands by workflow. Use it while practicing on a lab cluster (kind, minikube, or a sandbox).

Quick tips
- Set namespace for a session: `kubectl config set-context --current --namespace=<namespace>`
- Show resources across namespaces: `kubectl get pods -A` or `--all-namespaces`
- Rich output: `-o wide`, `-o yaml`, `-o json`, `-o jsonpath='<...>'`
- Learn object fields: `kubectl explain <resource>`

## Pod basics
- List pods: `kubectl get pods`
- Describe a pod: `kubectl describe pod <pod-name>`
- View logs: `kubectl logs <pod-name> [-c <container>]`
- Exec into a pod: `kubectl exec -it <pod-name> -- /bin/sh`
- Port-forward: `kubectl port-forward pod/<pod-name> <local-port>:<remote-port>`
- Copy to/from pod: `kubectl cp <src> <pod>:<dest>`

Examples
- Names only: `kubectl get pods -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}{end}'`
- Watch pods live: `kubectl get pods -w`

## Deployments & rollout
- List: `kubectl get deployments`
- Create/apply: `kubectl apply -f <file.yaml>`
- Update image: `kubectl set image deployment/<name> <container>=<image>`
- Scale: `kubectl scale deployment/<name> --replicas=<n>`
- Rollout status: `kubectl rollout status deployment/<name>`
- Rollback: `kubectl rollout undo deployment/<name>`

Best practice: use `kubectl apply` + declarative YAML for repeatable deployments.

## Services & networking
- List services: `kubectl get svc`
- Expose deployment: `kubectl expose deployment <name> --port=<port> --target-port=<target> --type=ClusterIP`
- Describe endpoints: `kubectl describe endpoints <service-name>`
- Ingresss: `kubectl get ingress` / `kubectl describe ingress <name>`

## Nodes
- List nodes: `kubectl get nodes`
- Drain a node: `kubectl drain <node> --ignore-daemonsets --delete-emptydir-data`
- Cordon/uncordon: `kubectl cordon <node>` / `kubectl uncordon <node>`

## Namespaces & contexts
- List namespaces: `kubectl get ns`
- Create: `kubectl create namespace <name>`
- Switch namespace for session: `kubectl config set-context --current --namespace=<name>`

## Troubleshooting & monitoring
- Client/cluster version: `kubectl version --short`
- Events: `kubectl get events --sort-by=.lastTimestamp`
- Pod resource usage (metrics-server): `kubectl top pods` / `kubectl top nodes`
- Restarting/CrashLoop analysis: `kubectl describe pod <pod>` and `kubectl logs --previous <pod>`

## Output examples
- YAML: `kubectl get <resource> -o yaml`
- JSONPath: `kubectl get pods -o jsonpath='{.items[*].status.phase}'`

Further reading
- Convert repetitive tasks into scripts or `kubectl` plugins.
- Official docs: https://kubernetes.io/docs/reference/kubectl/overview/
