config_replication
-----------

This use-case can be used to - 
1. Configure accounts and volumes on destination cluster for volume pairing
2. Configure cluster pairing between two NetApp Element clusters
3. Configure volume pairing between two volumes in different Element clusters

Usage
----

1. If you want to create accounts & volumes on destination Element cluster, set the config_dest_volumes variable to yes in vars/dest_vars.yml file  
2. Define the source volume and destination volume details for volume pairing in vars/pairing_vars.yml file for volume pairing
3. If you intend only to configure cluster pairing, go to config_replication_playbook.yml and comment out the volume pairing task
4. If you intend only to configure volume pairing, go to config_replication_playbook.yml and comment out the cluster pairing task
5. Run the playbook using the command - ansible-playbook config_replication_playbook.yml 
6. When prompted, provide destination and source cluster details
7. Once the playbook is successully completed, verify that the intended constructs are created in Element GUI
