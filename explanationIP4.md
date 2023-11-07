# Kubernetes Project Explanation

## Manifest Files

### backend.yml

The `backend.yml` manifest file includes the following components:

- **Deployment:** This resource defines the configuration for deploying the backend container. It specifies resource limits, container image, and ports.

- **Service:** The service resource exposes the backend container to other services within the cluster, allowing them to communicate through port 5000.

### frontend.yml

The `frontend.yml` manifest file comprises the following components:

- **Deployment:** This resource configures the deployment of the frontend application. It defines resource limits, container image, and ports.

- **Service:** The service resource exposes the frontend application, enabling other services in the cluster to access it via port 3000.

### volume.yml

The `volume.yml` manifest file is responsible for defining the following components:

- **Persistent Volume (PV):** This resource describes a persistent volume with specific storage attributes, such as capacity, access modes, and reclaim policies. In this case, it's a 1Gi storage volume using NFS with ReadWriteOnce access mode.

- **Persistent Volume Claim (PVC):** This resource requests storage resources from the PV. It's a placeholder for a PV with specific requirements, but the actual size is specified as `<Size>`.

### database.yml

The `database.yml` manifest file consists of the following components:

- **StatefulSet:** This resource defines a stateful set for the MongoDB database. It specifies the number of replicas, image used, and container ports.

- **Volume Claim Templates:** It defines the persistent volume claim templates that stateful set pods will use. It requests a storage of 1Gi with ReadWriteOnce access mode.

