create_config_cluster
-----------

This use-case can be used to configure SIP/cluster name on the storage nodes, create an Element cluster and configure the cluster parameters.

Usage
----

1. Define the cluster and node details in vars/main.yml for creating the cluster
2. Define the storage drive details in vars/main.yml file. If you want to add all drives from the nodes defined, then comment all lines in related to drives in vars/main.yml file.
3. If you want to create any extra networks/VLANs in the cluster, define the details in vars/main.yml file
4. Define the cluster parameters' details in vars/main.yml file
5. Define the MIP of one of the nodes that can be used for cluster create operation, username and password to be configured for the cluster in vars/main.yml
6. Run the playbook using - anisble-playbook create_config_cluster_playbook.yml -i hosts -u <<Element_cluster_username_to_be_configured>> -k
7. Verify that the cluster is created and intended logical constructs are created in the Element GUI
