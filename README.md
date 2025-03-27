# octo-waffle



Run the commands below to create the kubernetes namespace for kubestriker application

export K8S_NAMESPACE="kubestriker"
kubectl create namespace ${K8S_NAMESPACE}
dynamodb deployment
Run the below commands

kubectl create -f ./dependencies/dynamodb/kubestriker-db-service.yaml --namespace=${K8S_NAMESPACE}
kubectl create -f ./dependencies/dynamodb/kubestriker-db.yaml --namespace=${K8S_NAMESPACE}
neo4j backend service setup
kubectl create -f ./dependencies/neo4j/neo4j-common-config.yaml --namespace=${K8S_NAMESPACE}
kubectl create -f ./dependencies/neo4j/neo4j-core-config.yaml --namespace=${K8S_NAMESPACE}
kubectl create -f ./dependencies/neo4j/neo4j-discovery-lb.yaml --namespace=${K8S_NAMESPACE}
kubectl create -f ./dependencies/neo4j/neo4j-secret.yaml --namespace=${K8S_NAMESPACE}
kubectl create -f ./dependencies/neo4j/neo4j-service.yaml --namespace=${K8S_NAMESPACE}
kubectl create -f ./dependencies/neo4j/neo4j.yaml --namespace=${K8S_NAMESPACE} --validate=false
neo4j frontend service setup
kubectl create -f ./dependencies/neo4j-fe/neo4j-fe-service.yaml --namespace=${K8S_NAMESPACE}
kubectl create -f ./dependencies/neo4j-fe/neo4j-fe.yaml --namespace=${K8S_NAMESPACE} --validate=false
main kubestriker python container setup
kubectl create -f ./main/kubestriker-python/kubestriker-python-svc.yaml --namespace=${K8S_NAMESPACE}
kubectl create -f ./main/kubestriker-python/kubestriker.yaml --namespace=${K8S_NAMESPACE} --va
