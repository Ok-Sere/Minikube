# MINIKUBE

---

### **Project Overview**
This project provides a step-by-step guide to setting up **Minikube** on a Windows machine using **Git Bash**. Minikube is a tool that allows you to run a local Kubernetes cluster, which is essential for testing and developing Kubernetes applications.

The guide assumes the use of **Chocolatey**, a Windows package manager, to simplify the installation process. It also highlights the importance of enabling virtualization in your system BIOS, which is a prerequisite for running Minikube.

---

### **Detailed Steps**

#### **1. Prerequisites**
Before starting, ensure the following tools are installed and configured:

1. **Git Bash**: A terminal emulator for running Linux-like commands on Windows.
   - This is essential for executing the commands in the guide.
   
2. **Chocolatey**: A package manager for Windows.
   - The screenshot `1. choco.jpg` shows the Chocolatey installation process or its confirmation.

   ![Chocolatey Installation](./img/1.%20choco.jpg)

3. **Virtualization Support**: Ensure that virtualization is enabled in your system BIOS.
   - Virtualization is required to run virtual machines, which Minikube uses to create a local Kubernetes cluster.

---

#### **2. Installing Minikube**
The guide provides instructions to install Minikube using **Git Bash**:

1. Open **Git Bash** as an administrator.
   - This ensures the commands have the necessary permissions to execute.

2. Run the following command to install Minikube via Chocolatey:
   ```bash
   choco install minikube
   ```

   The screenshot `5. gitbash install.jpg` likely shows the command being executed in Git Bash.

   ![Git Bash Installation](./img/5.%20gitbash%20install.jpg)

---

#### **3. Managing Minikube Clusters**
1. **Starting Minikube**:
   Use the following command to start Minikube:
   ```bash
   minikube start
   ```

2. **Stopping Minikube**:
   The screenshot `6. stop.jpg` demonstrates how to stop Minikube. This is useful when you need to shut down the local Kubernetes cluster.
   ```bash
   minikube stop
   ```

   ![Stopping Minikube](./img/6.%20stop.jpg)

3. **Deleting Minikube**:
   To delete a Minikube cluster, use the following command:
   ```bash
   minikube delete
   ```
   This ensures that all resources created by Minikube are cleaned up.

---

#### **4. Viewing Kubernetes Nodes**
The screenshot `7. nodes.jpg` shows the output of a command to list the Kubernetes nodes. This confirms that Minikube is running and the cluster is operational.

   ```bash
   kubectl get nodes
   ```

   ![Kubernetes Nodes](./img/7.%20nodes.jpg)

---

#### **5. Describing a Node**
The screenshot `8. node describe.jpg` shows the output of a `kubectl describe node` command. This provides detailed information about a specific node in the Kubernetes cluster, such as its configuration, status, and resource usage.

   ```bash
   kubectl describe node <node-name>
   ```

   ![Node Description](./img/8.%20node%20describe.jpg)

---

### **6. Understanding Minikube's Scaling Limitations**
Minikube is designed for local development and testing, and it operates as a single-node Kubernetes cluster. This means it does not support multi-node clusters, which are essential for production environments. For scaling beyond a single node, consider using a cloud-based Kubernetes service or setting up a multi-node cluster with tools like **kubeadm**.

---

### **7. Node Upgrades and Version Alignment**
Minikube allows you to upgrade the Kubernetes version of your cluster. Keeping your cluster up-to-date ensures compatibility with the latest Kubernetes features and security patches. To upgrade Minikube, use the following commands:

1. Upgrade Minikube:
   ```bash
   minikube update-check
   minikube start --kubernetes-version=<desired-version>
   ```

2. Upgrade kubectl:
   ```bash
   choco upgrade kubernetes-cli
   ```

---

### **8. Summary and Key Takeaways**
- Minikube is a powerful tool for local Kubernetes development, but it is limited to single-node clusters.
- Use `kubectl` commands to manage and inspect nodes effectively.
- Minikube is not suitable for production environments due to its scaling limitations.
- Regularly upgrade Minikube and kubectl to ensure compatibility with the latest Kubernetes features.
- For production-level scaling, consider using cloud-based Kubernetes services or multi-node setups.

---



# Pods

---

### **Managing Kubernetes Pods**
Pods are the smallest deployable units in Kubernetes. They encapsulate one or more containers, storage resources, a unique network IP, and options for how the containers should run. Managing pods involves creating, inspecting, updating, and deleting them.

---

### **1. Viewing Pods**
The screenshot `9. po-a.jpg` shows the output of the `kubectl get pods` command. This command lists all the pods running in the Kubernetes cluster, along with their status, restart count, and age.

   ```bash
   kubectl get pods
   ```

   ![Viewing Pods](./img/9.%20po-a.jpg)

   This confirms that the pods are running and operational in the Minikube cluster.

---

### **2. Inspecting a Pod**
The screenshot `10. inspect a pod.jpg` demonstrates the output of the `kubectl describe pod <pod-name>` command. This command provides detailed information about a specific pod, including its events, resource usage, and container details.

   ```bash
   kubectl describe pod <pod-name>
   ```

   ![Inspecting a Pod](./img/10.%20inspect%20a%20pod.jpg)

   This is useful for troubleshooting and understanding the pod's configuration and runtime behavior.

---

### **3. Deleting a Pod**
To delete a pod, use the following command:

   ```bash
   kubectl delete pod <pod-name>
   ```

   This removes the specified pod from the cluster. If the pod is part of a deployment, Kubernetes will automatically recreate it to maintain the desired state.

---

### **4. Defining Pods in YAML**
Pods can be defined declaratively using YAML files. Below is an example of a simple pod definition:

   ```yaml
   apiVersion: v1
   kind: Pod
   metadata:
     name: example-pod
   spec:
     containers:
     - name: nginx-container
       image: nginx:latest
       ports:
       - containerPort: 80
   ```

   Save this file as `pod.yaml`.

---

### **5. Deploying Pods to Minikube**
To deploy the pod defined in the YAML file to Minikube, use the following command:

   ```bash
   kubectl apply -f pod.yaml
   ```

   This creates the pod in the Minikube cluster. You can verify its status using:

   ```bash
   kubectl get pods
   ```

---

### **6. Documenting Findings**
- **Pod Creation**: Pods can be created using `kubectl run` or YAML definitions. YAML provides a more structured and reusable approach.
- **Pod Management**: Use `kubectl get pods` to list pods, `kubectl describe pod` to inspect them, and `kubectl delete pod` to remove them.
- **Pod Behavior**: Pods are ephemeral. If a pod is deleted, it will not restart unless managed by a higher-level controller like a Deployment.
- **YAML Definitions**: YAML files allow you to define pods declaratively, making it easier to version control and share configurations.
- **Minikube Integration**: Minikube provides a local Kubernetes environment to test pod deployments and configurations before moving to production.

---

### **Conclusion**
This section expands on managing Kubernetes pods, defining them in YAML, and deploying them to Minikube. The screenshots and commands provide a clear understanding of pod operations, making it easier for users to manage their Kubernetes workloads effectively.


