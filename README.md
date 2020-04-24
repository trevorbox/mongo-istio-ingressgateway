# MongoDB deployment behind Service Mesh

This example shows how to deploy MongoDB behind Service Mesh on Openshift and open a NodePort on the mongo ingress gateway for external communication. With this configuration we can present a certificate in the mongo-ingressgateway proxy and test TLS connections from outside the mesh to MongoDB. A normal Openshift route does not support the mongo protocol.

## Install the Service Mesh
- Follow the README instructions in the service-mesh folder

## Install mongodb within its own Service Mesh
1. Login
```
oc login <mycluster>
```
2. Update playbook with appropriate k8s_namespace variable
3. Run playbook on cluster
```
ansible-playbook playbook.yml
```
4. Test normal connectivity to LoadBalancer
```
./scripts/ingress-mongodb-setup.sh
```
5. Test TLS connectivity to LoadBalancer
```
./scripts/ingress-mongodb-setup-tls.sh
```
