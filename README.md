# product-mongo

autoscaling mongodb configuration for the boerenboodschap/product-service microservice

## Setup

<!-- helm repo add percona https://percona.github.io/percona-helm-charts/
helm repo update

helm install my-op percona/psmdb-operator

helm install my-db percona/psmdb-db -->

helm repo add percona https://percona.github.io/percona-helm-charts/
<!-- helm install product-mongo-operator -f values.yaml percona/psmdb-operator --version 1.15.0 -->
helm install product-mongo-operator percona/psmdb-operator --version 1.15.0

helm install product-mongo percona/psmdb-db