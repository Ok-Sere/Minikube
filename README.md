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

#### **3. Stopping Minikube**
The screenshot `6. stop.jpg` appears to demonstrate how to stop Minikube. This is useful when you need to shut down the local Kubernetes cluster.

   ![Stopping Minikube](./img/6.%20stop.jpg)

---

#### **4. Viewing Kubernetes Nodes**
The screenshot `7. nodes.jpg` shows the output of a command to list the Kubernetes nodes. This confirms that Minikube is running and the cluster is operational.

   ![Kubernetes Nodes](./img/7.%20nodes.jpg)

---

#### **5. Describing a Node**
The screenshot `8. node describe.jpg` likely shows the output of a `kubectl describe node` command. This provides detailed information about a specific node in the Kubernetes cluster, such as its configuration, status, and resource usage.

   ![Node Description](./img/8.%20node%20describe.jpg)

---

### **Conclusion**
This guide walks users through the process of setting up Minikube on a Windows machine using Git Bash and Chocolatey. The screenshots provide visual confirmation of each step, making it easier for users to follow along and troubleshoot if necessary.