# SRE Runbook steps to resolve IT incidents

**Issue** : Erroneous Call rate is too high

**Description** : Service impact - Resolving an issue where the call rate is
erroneously high requires identifying the underlying cause and
implementing appropriate solutions. High call rates can lead to
performance problems and system instability. Here are steps to resolve
this issue:

**Resolution Steps** :
To check if a Kubernetes deployment is down, you can use various
`kubectl` commands to inspect the status of your deployment. Here
are some useful commands to be executed after setting Kubernetes
context to the namespace of your application using `kubectl config set-
context --current --namespace=<namespace-name>`:

1. Check Deployment Status:
`kubectl get deployments`
This command will list all the deployments in your cluster along with
their current status. Look for your specific deployment and check if the
desired and current replica counts match.
2. Check Pod Status:
`kubectl get pods`
Use this command to list all pods in your cluster. Inspect the status
column to see if any pods associated with your deployment are in a
state other than "Running" or "Completed."
3. Describe Deployment:
`kubectl describe deployment <deployment-name>`
Replace `<deployment-name>` with the name of erroneous
deployment. This command provides detailed information about your
deployment, including events and conditions.
4. Check ReplicaSets:
` kubectl get replicasets`
This command lists all ReplicaSets in your cluster. Ensure that the
pods controlled by your deployment are part of a healthy ReplicaSet.


5. Logs from Pods:
`kubectl logs <pod-name>`
Replace `<pod-name>` with the name of one of the pods from your
deployment. Inspect the logs to identify any issues or error messages
that might indicate why the deployment is not working as expected.
6. Check Events:
`kubectl get events`
This command displays cluster events. Look for events related to your
deployment to identify any issues or error messages.
7. Check Service Status:
` kubectl get services`
If your deployment is associated with a service, ensure that the
service is running and has the correct endpoints.
8. Health Probes:
If your deployment has liveness and readiness probes defined, check
their status:
`kubectl describe pod <pod-name>`
Look for the status of the liveness and readiness probes to ensure
they are passing.
9. Increase initialDelaySeconds in the relevant deployment if the logs
suggest failure of readiness probe and connection refused erros.

These commands should give you a good starting point to diagnose and
identify the issues with your Kubernetes deployment and hence
resolving. Adjust the commands based on your specific deployment
configuration and requirements.

**Issue** : Available replicas is less than desired replicas.

**Description** : The "Available replicas is less than desired replicas" error
in a Kubernetes environment typically indicates that your application's
deployment or stateful set is unable to meet the specified number of
desired replicas due to various issues. To resolve this error, you'll need
to investigate the root cause and take appropriate actions. Here are
steps to help you resolve this issue:

**Resolution Steps** :


1. Check Resource Availability:
- Ensure that your Kubernetes cluster has enough resources (CPU,
memory, etc.) to accommodate the desired number of replicas.
Insufficient resources can prevent pods from running.
2. Review Pod Logs:
- Check the logs of the pods that are failing to start or are being
terminated. Logs may contain error messages or information that can
help you identify the underlying issue.
3. Check Resource Requests and Limits:
- Review the resource requests and limits defined in your pod or
container specifications. Ensure they are set appropriately to avoid
resource contention. Incorrect values can cause pods to fail.
4. Inspect Events and Describe Pods:
- Use `kubectl describe` and `kubectl get events` to gather more
information about the pods and deployment. This can provide insights
into events or errors related to pod creation and termination.
5. Examine Configurations:
- Verify that your deployment or stateful set configurations are correct.
Pay attention to the number of desired replicas, selector labels, and the
template specifications.
6. Check for Pending Pods:
- Use `kubectl get pods` with the `-o wide` option to see if any pods
are in a "Pending" state. Pending pods may be waiting for resources or
conditions to become available.
7. Check Node Health:
- Ensure that your cluster nodes are healthy and not experiencing
issues such as disk pressure or network problems, which can affect pod
scheduling.
8. Scale Down and Scale Up:
- If you're running into resource constraints, consider scaling down the
number of replicas temporarily to free up resources. Once resources are
available, scale the replicas back up.
9. Check for Custom Resource Definitions (CRDs):
- If you are using Custom Resource Definitions, make sure that the
controllers responsible for managing them are running correctly. Issues
with CRD controllers can impact the deployment of resources.
10. Inspect Taints and Tolerations:


- If you're using node taints and pod tolerations, make sure they are
configured correctly. Misconfigured taints or tolerations can prevent
pods from scheduling.

**Issue** : Calls are slower than usual.

**Description** : Application slow response - Resolving an incident where
calls to an application are taking more than 1 second to return on
average involves a systematic troubleshooting and optimization
process. Here are steps to help you resolve this issue.

**Resolution steps** :

1. Identify the Problem Scope:
- Determine if the issue is affecting a specific component, service, or the
entire application. This will help you narrow down the investigation.
2. Resource Utilization:
- Monitor CPU and memory usage of application. Due to increased load
and high resource utilization slow response times are caused. Consider
scaling resources as needed. Execute scale-up-robot-shop action to
scale up resources of robot-shop application.
3. Network and External Dependencies:
- Check the network latency and connectivity to external services or
dependencies. Slow or unreliable network connections can lead to slow
response times.
4. Database Performance:
- If your application relies on a database, investigate database
performance. Slow database queries can significantly impact
application response times. Optimize queries and indexes if needed.
5. Caching Strategies:
- Implement caching mechanisms to reduce the load on the application
and improve response times for frequently requested data.

**Issue** : Abnormal termination - Process exited as a result of an uncaught
signal: SIGKILL.

**Description** : The "Process exited as a result of an uncaught signal:
SIGKILL" error in a Kubernetes pod typically indicates that the container
or process running within the pod was forcefully terminated by the


Kubernetes system or another entity. SIGKILL is a signal that cannot be
caught, blocked, or ignored by the process, and it usually occurs due to
resource constraints or other exceptional situations. To resolve this
error, you need to investigate the root cause and take appropriate
actions:
Resolution steps:

1. Identify the Affected Pod:
- Use `kubectl get pods` and `kubectl describe pod <pod-name>` to
identify the pod that is experiencing the "SIGKILL" issue.
2. Check Resource Requests and Limits:
- Review the resource requests and limits defined in your pod or
container specifications. Ensure they are set appropriately to prevent
resource starvation. If resource limits are too low, the pod may be
terminated due to resource constraints.
3. Inspect Resource Usage:
- Use `kubectl top pod <pod-name>` to monitor the resource
utilization of the pod, including CPU and memory usage. Check if the
pod is consistently exceeding its resource limits.
4. Check Node Resource Availability:
- Ensure that the Kubernetes nodes in your cluster have sufficient
resources (CPU, memory, etc.) available to accommodate the pod's
resource requests.
5. Review Resource Quotas:
- Verify that Resource Quotas (RQs) and LimitRanges (LRs) applied to
the namespace where the pod is deployed are correctly configured.
Resource quotas can limit resource consumption.
6. Check for Eviction Events:
- Look for Kubernetes events related to pod evictions. You can use
`kubectl describe node <node-name>` to check for events indicating
resource pressure or node issues.
7. Inspect Node Conditions:
- Use `kubectl describe node <node-name>` to check the status of
node conditions, especially conditions related to disk pressure, memory
pressure, or system stability.
8. Implement Horizontal Pod Autoscaling (HPA):
- If your application experiences fluctuating resource demands,
consider implementing Horizontal Pod Autoscaling (HPA) to


automatically adjust the number of replicas based on resource
utilization.

**Issue** : Out of Memory

**Description** : Resolving an "out of memory" issue in a Kubernetes
environment requires a systematic approach to identify the root cause
and implement effective solutions. Here are steps to resolve memory-
related problems in a Kubernetes cluster:

**Resolution Steps** :

1. Identify the Affected Pods:
- Use `kubectl get pods` to list all pods in the namespace, and identify
which pods are experiencing memory-related issues.
2. Check Resource Requests and Limits:
- Review the resource requests and limits defined in your pod or
container specifications.Ensure they are set appropriately to prevent
resource starvation. Adjust these values if necessary.
3. Inspect Memory Usage:
- Use `kubectl top pod <pod-name>` to monitor the memory utilization
of the affected pods. Check if the pods consistently exceed their
memory limits.
4. Review Resource Quotas:
- Verify that Resource Quotas (RQs) applied to the namespace where
the pod is deployed are correctly configured and that there is sufficient
memory quota available.
5. Check Node Resource Availability:
- Ensure that the Kubernetes nodes in your cluster have enough
memory available to accommodate the pod's resource requests and
limits.
