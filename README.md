# Kubernetes-Cluster-on-AWS-with-Terraform-and-DaemonSet
Link For Packages and report of this Lab: https://drive.google.com/file/d/1gZcehzjXfIY8jFxQUXVSrYowdpekdqw4/view?usp=drive_link
Deployed a Kubernetes cluster on AWS using Terraform with 1 master and 2 worker nodes. Initialized K8s using kubeadm, verified setup via kubectl. Deployed a DaemonSet to run pods on all nodes. Validated service on port 1233 through browser access using public IPs of master and worker nodes.

This lab focused on deploying a Kubernetes cluster on AWS using Terraform to automate infrastructure provisioning. The setup included one master node and two worker nodes, each launched on separate EC2 instances. Using Infrastructure as Code (IaC), resources such as VPCs, subnets, security groups, and EC2 instances were defined and created consistently using Terraform scripts.

After the infrastructure was deployed, the Kubernetes control plane was initialized on the master node using kubeadm init with a custom configuration file. The worker nodes were then joined to the cluster using the join command provided during the initialization process.

Post setup, standard Kubernetes commands were used to verify the cluster status. kubectl get nodes confirmed that all nodes were properly registered and in a 'Ready' state. kubectl get services was used to list active services running in the cluster.

To demonstrate workload deployment across all nodes, a Kubernetes DaemonSet was configured. This ensured a specific pod ran on every node, showcasing Kubernetes' native capability to manage distributed services like log collection or monitoring agents.

A basic web application was exposed on port 1233. The service was validated by accessing the application via browser using both the master and worker public IPs. This confirmed correct port exposure and network routing.

Overall, this lab highlighted the power of Terraform for automated cloud infrastructure provisioning and the flexibility of Kubernetes in managing scalable, distributed workloads.
