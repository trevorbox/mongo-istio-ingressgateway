# Install Service Mesh Operators and create the Control Plane


> mTLS disabled


## Install Service Mesh Operators
1. Ensure you are logged in
```
oc login <mycluster>
```
2. Run the playbook
```
ansible-playbook 01_playbook-install-service-mesh.yml
```

## Install Control Plane
Choose whether to install the mongo control plane.
- Default Control Plane:
   1. Ensure you are logged in
      ```
      oc login <mycluster>
      ```
   2. Update `control_plane_namespace` within *02_playbook-install-control-plane.yml* with desired project name to deploy too
   3. Run the playbook
      ```
      ansible-playbook 02_playbook-install-control-plane.yml
      ```
