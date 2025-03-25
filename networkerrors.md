Major networking errors related to

1. DNS Resolution
2. Network Policy
3. POD-POD communication
   
Symptoms:
Pods on different nodes or within the same node cannot communicate with each other.
Troubleshooting Steps:
Check Pod Network Configuration: Ensure the network plugin (e.g., Calico, Flannel, Weave) is correctly installed and running.
**kubectl get pods -n kube-system**
Look for networking-related pods like calico-node or flannel. Verify Network Policies: Check if there are any restrictive NetworkPolicies that prevent communication between Pods.
**kubectl get networkpolicy**
If a NetworkPolicy is present, verify the allowed ingress and egress rules.
Check CNI Plugin Logs: If using a CNI (Container Network Interface) plugin like Calico or Flannel, check its logs for errors.
**kubectl logs <cni-pod-name> -n kube-system**
Verify IP Routing and DNS Resolution: Ensure that IP routing is set up correctly and DNS resolution is working.
**kubectl exec <pod-name> -- nslookup <other-pod-name>**


5. Persistant Volume mount failure
6. Unavailable Nodes
7. Failed Readiness Probe
8. Connection Timeout
9. Firewall rules block overlay network traffic
10. POD CIDR Conflicts
