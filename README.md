# product-mongo

autoscaling mongodb configuration for the boerenboodschap/product-service microservice

## Status

The helm chart breaks when trying to connect to it.

The configuration in the config directory works but has a lot of setup work.

## Setup

<!-- helm repo add percona https://percona.github.io/percona-helm-charts/
helm repo update

helm install my-op percona/psmdb-operator

helm install my-db percona/psmdb-db -->

helm repo add percona https://percona.github.io/percona-helm-charts/
<!-- helm install product-mongo-operator -f values.yaml percona/psmdb-operator --version 1.15.0 -->
helm install product-mongo-operator percona/psmdb-operator --version 1.15.0

helm install product-mongo percona/psmdb-db