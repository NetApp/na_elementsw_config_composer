scale_cluster
-----------

This use-case can be used to scale an existing NetApp Element cluster.

Usage
----

1. Define the details of nodes to be added to an existing cluster in vars/main.yml
2. Define the storage drive details in vars/main.yml file. 
3. Define the cluster MVIP in hosts file
4. Run the playbook and provide the Element password when prompted - anisble-playbook scale_cluster_playbook.yml -i hosts -u <<element_username>> -k 
5. Verify that the intended nodes are added to the Element cluster
