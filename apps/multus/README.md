# multus

Multus CNI is a container network interface plugin for Kubernetes that enables attaching multiple network interfaces to pods.

source: [GitHub](https://github.com/k8snetworkplumbingwg/multus-cni)

## Opinion

Multus provides a “quickstart” deployment YAML that is intentionally minimal. While the Multus team notes that comprehensive deployment should be handled by each platform, in my opinion, this is a minor drawback. Multus is small and simple enough that a more complete and user-friendly installation option—such as separating CRDs from other manifests or providing a Helm chart—would be feasible and improve usability.

Aside from this, the software is excellent!
