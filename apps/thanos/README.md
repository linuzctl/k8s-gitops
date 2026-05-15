# thanos

Thanos is an open-source CNCF incubating project that transforms Prometheus into a highly available, globally queried, long-term metric storage system. It acts as a set of components placed on top of existing Prometheus deployments, providing unlimited retention in S3-compatible object storage and a unified query view across multiple clusters.

source: [GitHub](https://github.com/thanos-io/thanos)

## opinion

I decided to switch from Mimir to Thanos due to performance and resource requirements. Mimir is a powerful solution, but it is quite large and complex for use with only one or two Kubernetes clusters. For my needs, Thanos is a better fit, offering the right balance of features and scalability.

I also considered VictoriaMetrics because of its very low CPU and RAM requirements. However, VictoriaMetrics does not support storing data in an object store, and I prefer not to keep all metrics data locally. This was the main reason why Thanos became the best choice for my setup.
