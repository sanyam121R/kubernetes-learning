# Kubernetes

## deploying a MySQL database instance on K8s using persistent volumes

This feature enables stateful apps to overcome the inherent transience of the K8s pods.

- A Kubernetes secret for storing the database password.
- A Persistent Volume (PV) to allocate storage space for the database.
- A Persistent Volume Claim (PVC) that will claim the PV for the deployment .
- The deployment itself.
- The Kubernetes Service.

### Step 1: Create Kubernetes Secret

`nano mysql-secret.yaml`

save the file and then apply the yaml file using the following command

`kubectl apply -f mysql-secret.yaml`

### Step 2: Create Persistent Volume and Volume Claim

The first part defines the Persistent Volume

Create the storage configuration file:
`nano mysql-storage.yaml`
save the file and then apply the yaml file using the following command
`kubectl apply -f mysql-storage.yaml`

### Step 3: Create MySQL Deployment

Create the deployment and apply the file with kubectl:
`kubectl apply -f mysql-deployment.yaml`

## Access Your MySQL Instance

- To access the MySQL instance, access the pod created by the deployment.
List the pods with kubectl:

`kubectl get pod`

- Get a shell for the pod by executing the following command:

`kubectl exec --stdin --tty mysql-694d95668d-w7lv5 -- /bin/bash`

- Type the following command to access the MySQL shell:

`mysql -p`
