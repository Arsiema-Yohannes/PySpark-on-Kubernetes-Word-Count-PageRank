# Apache Spark Project

## Overview
This project utilizes Apache Spark to process and analyze large datasets efficiently. It is designed to handle real-time data and perform complex analytics, leveraging Kubernetes and Helm for orchestration and deployment.

## Features
- **Real-time Data Processing:** Efficient handling of streaming data using Apache Spark.
- **Scalability:** Deployed on Kubernetes, allowing for easy scaling and management.
- **User-Friendly Interface:** Designed to facilitate seamless interaction with data analytics tools.

## Getting Started

### Prerequisites
- [Docker](https://www.docker.com/get-started)
- [Kubernetes](https://kubernetes.io/docs/setup/)
- [Helm](https://helm.sh/docs/intro/install/)

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/your-repo-name.git
   cd your-repo-name
2. Deploy the NFS server:
   helm repo add stable https://charts.helm.sh/stable
   helm install nfs stable/nfs-server-provisioner --set persistence.enabled=true,persistence.size=5Gi

3. Deploy the Spark application:
   kubectl apply -f spark-deployment.yaml

Running the Application
To run a Spark job, use the following command:
kubectl run --namespace default spark-client --rm --tty -i --restart='Never' \
--image docker.io/bitnami/spark:3.5.1-debian-12-r7 -- \
spark-submit --master spark://<spark-master-ip>:7077 \
--deploy-mode cluster --class org.apache.spark.examples.JavaWordCount \
/data/my.jar /data/test.txt


Acknowledgments
Apache Spark
Kubernetes
Helm
