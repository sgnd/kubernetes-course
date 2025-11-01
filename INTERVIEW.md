
# Kubernetes Interview Questions — organized by topic

Use these questions to structure study sessions. Grouped from foundational to advanced, they’re suitable for self-study or mock interviews.

## Core concepts & architecture
- What is Kubernetes and which problems does it solve?
- Describe the control plane components (kube-apiserver, etcd, kube-scheduler, controller-manager) and their responsibilities.
- What is etcd and why is it critical? How would you back it up and restore it?
- How does the kube-scheduler make placement decisions?
- How do you design for control-plane and etcd high availability?

## Pods, controllers & workloads
- What is a Pod and how does it differ from a container?
- When to use Deployment, StatefulSet, DaemonSet, Job, and CronJob?
- How do rolling updates, rollbacks, and rollout strategies work?
- How do readiness and liveness probes affect rolling updates and traffic?

## Services, networking & ingress
- How does Service-based discovery and ClusterIP work?
- Compare ClusterIP, NodePort, and LoadBalancer service types.
- What is an Ingress and when would you use it vs a Service?
- How would you implement network policies to restrict traffic?

## Storage & stateful workloads
- Explain PersistentVolume (PV) and PersistentVolumeClaim (PVC) lifecycle.
- How do StatefulSets manage identity and storage persistence?
- What are StorageClasses and reclaim policies?

## Security & access control
- Explain RBAC: Roles, ClusterRoles, RoleBindings and ClusterRoleBindings.
- How do you secure cluster components and kube-apiserver access?
- Best practices for secrets management and preventing privilege escalation.

## Observability & troubleshooting
- How do you collect logs and metrics from Kubernetes workloads?
- How would you debug a failing Pod or a CrashLoopBackOff?
- When to use events vs metrics vs tracing for troubleshooting?

## Scaling, autoscaling & availability
- How does Horizontal Pod Autoscaler (HPA) work? What metrics can it use?
- When would you use Vertical Pod Autoscaler (VPA) or Cluster Autoscaler?
- Strategies for application and cluster high availability.

## CI/CD, GitOps & operations
- How do you integrate Kubernetes with CI/CD pipelines (example patterns)?
- What is GitOps and how does it help manage clusters?
- How do you perform safe cluster upgrades and node maintenance?

## Advanced & extensibility
- When to implement a CustomResourceDefinition (CRD) and controller?
- Design considerations for multi-tenant clusters and resource quotas.
- Running specialized workloads: stateful databases, ML training, batch jobs — what changes?

## Study tips
- Practice with small labs: deploy an app, add monitoring, break networking, and fix it.
- Turn questions into hands-on tasks (e.g., implement a canary deploy).
- Read the API reference and controller docs for deeper understanding.
