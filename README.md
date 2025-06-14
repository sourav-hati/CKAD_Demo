Here’s a comprehensive list of mock questions for the Certified Kubernetes Application Developer (CKAD) exam, covering the key domains from the official CNCF CKAD curriculum:

🧠 1. Core Concepts (13%)
Create a pod with the image nginx:1.25.0 and expose it on port 80.

What is the difference between a Pod and a Deployment?

Create a multi-container pod where both containers share the same volume.

Use a command to list all the pods in the namespace development.

Write a YAML manifest for a pod that runs an init container before the main app.

⚙️ 2. Configuration (18%)
Create a ConfigMap named app-config with key APP_MODE=debug.

Mount a Secret named db-secret into a pod as environment variables.

How do you configure a pod to use a ConfigMap as a mounted volume?

Create a Secret from literal values for database username and password.

Patch a running Deployment to change the image version without downtime.

📦 3. Multi-Container Pods (10%)
Create a pod with:

A main container (app)

A sidecar container (log-agent)

A shared volume for logs

How does a sidecar container help in microservices architecture?

Which fields in a pod spec enable two containers to communicate via shared volume?

🧪 4. Observability (18%)
Use kubectl to view logs of a pod named web-app.

Create a liveness probe for a pod that checks /healthz endpoint on port 8080.

How do you set a readiness probe to wait for a pod to be fully started?

Get metrics for all nodes and pods using kubectl top.

What is the output of kubectl describe pod useful for?

🔁 5. Pod Design (20%)
Create a Deployment with 3 replicas and rolling update strategy.

Use affinity to ensure pods are scheduled on separate nodes.

Set up a job to run a batch process once and exit.

Design a CronJob to run every hour.

Define a pod that mounts an emptyDir volume for temporary file storage.

🌐 6. Services & Networking (13%)
Expose a pod using a ClusterIP service on port 8080.

Create an Ingress resource to expose a web app at /app path.

What’s the difference between NodePort, ClusterIP, and LoadBalancer services?

Configure NetworkPolicy to allow ingress traffic only from a certain pod label.

How do services discover other services in the same namespace?

🧪 7. State Persistence (8%)
Create a pod that uses a PersistentVolumeClaim.

Define a PVC for 5Gi of storage in ReadWriteOnce mode.

What happens to data in emptyDir if the pod restarts?

Mount a hostPath volume into a pod for local testing.

⚡ Bonus: Practical Task Challenge Questions
Scale a Deployment named api-deploy to 5 replicas.

Delete all pods in the namespace staging without deleting the namespace.

Create a namespace ckad-practice and set it as default.

Debug a CrashLoopBackOff pod and suggest fixes.

Use kubectl cp to copy a file into a pod.

Create a deployment using imperative command with kubectl run.

Would you like these as a downloadable PDF, Markdown, or CSV/Excel file for practice tracking? Or need answers + manifests for hands-on prep?


🔄 Advanced & Scenario-Based CKAD Mock Questions
🧠 Core Concepts (continued)
Create a Deployment using the busybox image that runs sleep 3600 as a command.

Use kubectl explain to check the field under spec.template.spec.containers that defines the container image.

What field would you use to ensure pod restarts on failure?

⚙️ Configuration (continued)
Create a ConfigMap from a file called settings.env.

Inject a ConfigMap key as an environment variable into a container.

Update a ConfigMap without restarting the pod.

Mount a Secret in a pod as a file and show the default file permissions.

How can you make a pod access a ConfigMap from a different namespace?

📦 Multi-Container Pods (continued)
Design a pod with:

Main app container

Init container to fetch config from a remote URL

Create a pod where a container logs to /var/log/app.log and a sidecar tails the file.

What’s the lifecycle order of init containers and main containers?

🧪 Observability (continued)
Use a readiness probe with an initial delay of 5 seconds and timeout of 2 seconds.

What is the difference between liveness and readiness probes?

Use kubectl events to troubleshoot a failing pod.

Describe a situation where kubectl logs -p is used.

Use an exec probe to run a health check script inside a pod.

🔁 Pod Design (continued)
Use resource limits and requests in a pod spec.

Create a DaemonSet that runs fluentd on each node.

Run a pod with anti-affinity rules using labels to avoid same-node scheduling.

Create a job that retries failed pods 3 times.

Use lifecycle hooks (preStop, postStart) in a pod.

🌐 Services & Networking (continued)
Debug a service that isn't routing to its backend pods.

Create a headless service and explain when it is used.

Use labels and selectors to bind a service to specific pods.

Allow egress traffic only to port 443 using a NetworkPolicy.

What’s the default DNS name resolution for a service inside a namespace?

🧪 State Persistence (continued)
Bind a PVC to a specific StorageClass.

Set up a StatefulSet with volume claim templates.

Create a pod that uses both hostPath and persistentVolumeClaim.

Delete a pod and verify persistent data is retained in the volume.

Show the YAML fields that define volume mounts and volume definitions separately.

💡 Combined Task-Based Exercises (Full Workflow Simulation)
Create a namespace project-x. In this namespace:

Deploy a pod running nginx

Create a ConfigMap for environment config

Mount the ConfigMap into the pod

Expose it via a ClusterIP service

Add a readiness probe to check /status

Create a CronJob that:

Runs every 5 minutes

Runs a curl command to an internal service

Logs output to a shared volume

Migrate a pod from using environment variables to using ConfigMaps and Secrets instead.

Create a rolling update strategy where:

Max surge = 1

Max unavailable = 0

A pod needs access to both a private key (Secret) and a license file (ConfigMap). Mount both in different paths.

Debug: A Deployment has 3 pods, but only 1 is running. Identify and fix the issue using kubectl and pod events.

✅ Do You Want:
All questions with answers?

Real YAML manifest samples?

CLI commands per question?

Delivered in a PDF/Excel format?

Let me know and I’ll prepare a downloadable CKAD Practice Kit just for you.
🧠 76–125: Extended CKAD Mock Questions
📚 Core Concepts (continued)
Create a pod that uses a non-root user and prevents privilege escalation.

What happens if two pods share the same labels but belong to different deployments?

Create a Deployment and verify it uses the latest ReplicaSet.

Identify which ReplicaSet a running pod belongs to.

Delete a ReplicaSet but keep its pods running.

⚙️ Configuration (continued)
Create a Secret from a .env file and mount it as a volume.

Modify an environment variable in a pod using kubectl patch.

Validate a YAML manifest before applying it.

Use a downward API to expose the pod name and namespace as environment variables.

Load an entire directory as multiple config keys into a ConfigMap.

📦 Multi-Container Pods (continued)
Create a multi-container pod where one container serves files and the other watches for changes.

Define readiness and liveness probes for both containers in a multi-container pod.

Configure a shared log volume for audit collection between containers.

What happens if one container in a multi-container pod crashes?

Use a lifecycle hook in a sidecar container to delay startup.

🧪 Observability (continued)
Use kubectl get events --sort-by=.metadata.creationTimestamp to debug slow pod startup.

Explain the lifecycle stages visible in pod conditions.

What does a pod's Terminated state indicate?

Use kubectl logs -c <container> to view logs from a specific container in a pod.

Create a probe with custom headers and initial delay.

🔁 Pod Design (continued)
Create a pod that runs a sleep command and exits after 10 seconds (simulate short-lived job).

Use restartPolicy: OnFailure for a job that retries on exit code != 0.

Create a job that completes only if a pod returns exit code 0.

Use pod affinity to co-locate related pods on the same node.

Modify the revisionHistoryLimit for a deployment to keep only 2 previous ReplicaSets.

🌐 Services & Networking (continued)
Write an Ingress definition for two services exposed at different paths.

Create a service without a selector and manually associate an endpoint.

How would you expose a legacy app that runs on NodePort using Ingress?

Create a NetworkPolicy that denies all ingress and egress, then allow from a specific pod.

Describe how to connect pods in different namespaces securely.

🧪 State Persistence (continued)
Create a PVC that binds to a pre-provisioned PV.

Use a hostPath volume in read-only mode.

Create a StatefulSet with pod volume claim templates.

Simulate a PVC being bound to the wrong PV and resolve it.

Change the StorageClass of a PVC post-deployment.

🔄 Troubleshooting & Real-World Scenarios
A pod is in CrashLoopBackOff — how do you debug it?

Your deployment isn't scaling — identify cause using kubectl describe.

A liveness probe is killing your pod every minute — adjust configuration.

A ConfigMap update isn't reflected in your pod — what's wrong?

NetworkPolicy is blocking traffic — how to verify and fix it?

🛠️ Imperative Commands Practice
Create a deployment using CLI with 2 replicas of httpd.

Expose the deployment as a ClusterIP service on port 8080.

Scale the deployment to 5 replicas using the command line.

Create a configmap and mount it in a pod using only CLI (no YAML).

Run a debug pod using kubectl run with --rm -it for temporary troubleshooting.

📦 YAML & Practical Workflows (mini case studies)
You need to deploy a stateless app:

Use a configmap

Expose via service

Add readiness probe

Use resource limits
✅ Create all YAMLs in one file

Simulate rolling update:

Create deployment

Trigger rollout

Undo rollout
✅ Show CLI steps

Migrate a pod:

From using hardcoded environment values

To use ConfigMap and Secret volumes instead

Create a pod that:

Logs to a shared volume

Automatically deletes after success

Has CPU and memory limits

Create a CronJob that:

Runs a wget to a healthcheck URL

Logs output to a volume

Runs every 15 minutes









