# aistor-operator

The MinIO AIStor Operator manages MinIO AIStor deployments on Kubernetes clusters using the Kubernetes Operator pattern. The Operator automates deployment, configuration, and lifecycle management tasks for MinIO AIStor, reducing operational complexity when running on Kubernetes.

source: [GitHub](https://github.com/minio/helm)

## opinion

MinIO recently sent a strong signal to the open-source community with a simple [README.md update](https://github.com/minio/minio/commit/27742d469462e1561c776f88ca7a1f26816d69e2). Unfortunately, that change also undermined its position as the go-to object storage solution for many users, including myself. At the moment, there doesn’t seem to be a clear, mature alternative in the open-source space. Projects like [Garage](https://github.com/deuxfleurs-org/garage), [RustFS](https://github.com/rustfs/rustfs), and [versitygw](https://github.com/versity/versitygw) are being discussed, but it’s still too early to tell which, if any, will emerge as a stable and widely adopted successor. For now, I’m stuck using MinIO AIStor under the free license, despite my reservations. Also… what’s going on with the naming scheme? “AIStor” sounds like something an AI came up with rather than a product with a clear identity.
