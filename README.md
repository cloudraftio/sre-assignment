### 🚀 SRE Assignment

#### **Objective**
Deploy a containerized app that exposes a `/counter` endpoint using Helm, ArgoCD, and KIND, and investigate any issues with the app behavior. 

Correct Behaviour:
```
curl localhost/counter
Counter value: 1
curl localhost/counter
Counter value: 2
curl localhost/counter
Counter value: 3
curl localhost/counter
Counter value: 4
...
```

### **📋 Task Details**

#### **1. Helm Chart Creation**
- Create a Helm chart named `metrics-app`.
- The app is hosted at: `ghcr.io/cloudraftio/metrics-app:1.1`
- It runs on port `8080` and exposes a `/counter` endpoint.
- App needs a secret `PASSWORD` set to `MYPASSWORD`, available as an environment variable. How do you ensure that it is not written in git repo?


#### **2. Local KIND Cluster Setup**
- Set up a local Kubernetes cluster using [Kind](https://kind.sigs.k8s.io/).
- Install ArgoCD on this cluster.
- Configure ArgoCD to watch a Git repository containing your Helm chart.

#### **3. App Deployment**
- Use ArgoCD to deploy the app via the Helm chart, keeping best practices in mind.

#### **4. Ingress Setup**
- Set up an ingress resource (e.g., NGINX ingress controller) to expose the app externally at:
  ```
  http://<your-local-url>/counter
  ```


#### **5. Document the Behaviour**
- Observe the behavior of the `/counter` endpoint when calling it multiple times.
  Validate the response by accessing the URL *multiple times*. What is the response to each call? 
  `curl localhost:8080/counter`
  `curl localhost:8080/counter`
  `curl localhost:8080/counter`
  `curl localhost:8080/counter`
- Note any anomalies or inconsistent or slow responses.
- Document your debugging process.

#### **6. Root Cause Analysis**
- Identify and document the root cause if any issues are found.
- Could you suggest or implement a fix if appropriate?

---

### ✅ **Submission Guidelines**
- Submit via email:
  - Git repository link with:
    - Helm chart
    - ArgoCD configuration (`Application` manifest, etc.)
    - Ingress 
    - Any scripts/configs used to bootstrap the KIND + ArgoCD setup
  - Documentation
    - Deployment steps
    - Any issues found and how they were diagnosed
    - Root cause analysis if you find an issue.
    - Screenshots/logs as evidence
- **Bonus Points** for using best practices.
