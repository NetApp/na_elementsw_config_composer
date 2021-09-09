na_elementsw_config_composer
=========


This ansible content can be used to setup and configure the NetApp Element cluster [4-node or higher]

This is a tasks repository and requires some grouping effort to use it

    Based on the use-case or workflow, group different tasks into a playbook and use the playbook to achieve desired result
    Copy the variables related to the tasks you wish to group from the corresponding variable files and fill the variables with necessary information
    Use those variable files in the playbook where you group the different tasks
    
    use-cases folder houses examples of the usual workflows
    Use the examples as a baseline to build upon more complex workflows 
    To secure credentials, use ansible vault or vars_prompts or provide credentials on run using -u and -k flags with ansible-playbook command

License
------

By accessing, downloading, installing or using the content in this repository, you agree the terms of the License laid out in [License](license.txt) file.

Note that there are certain restrictions around producing and/or sharing any derivative works with the content in this repository. Please make sure you read the terms of the [License](license.txt) before using the content. If you do not agree to all of the terms, do not access, download or use the content in this repository.

Requirements
------------

    Ansible version: 2.9 and above

    The NetApp Element storage nodes must be initialized before using this ansible content
    The nodes need to be configured with network configuration for Bond1G interfaces i.e. Management IPs for all storage nodes must be configured
    The management IPs of the storage nodes must be reachable from the Ansible host running the playbook
    The storage nodes must be able to ping each other
    solidfire-sdk-python version 1.5.0.87.post1, requests must be installed on the ansible machine and enum34 must be uninstalled. These tasks can be performed by running the  pre_reqs playbook as root by providing root password - ansible-playbook pre_reqs.yml -K  
    netapp.elementsw collections must be installed - ansible-galaxy install -r collections/requirements.yml OR ansible-galaxy collection install netapp.elementsw
 

Role Variables
--------------


Refer the vars folder for information on task variables


Tags Info
---------

    add_drives: To add drives to the Element cluster
    config_cluster: To configure the Element cluster parameters
    create_access-groups: To create and configure access-groups in Element cluster
    create_account: To create accounts in Element cluster
    create_cluster_pairs: To create and configure cluster pairs in Element clusters
    create_cluster: To create a Element cluster
    create_initiators: To create iSCSI initiators in Element cluster
    create_snapshot_schedule: To create snapshot schedule for the volumes in Element cluster
    create_snapshot: To create a snapshot of volumes in Element cluster
    create_vlan: To create additional storage network or VLAN in Element cluster
    create_volume_pairs: To create and configure volume pairs in Element cluster
    create_volumes: To create and configure volumes in Element cluster
    create_qos_policy: To create qos policies for configuring it with volumes in Element cluster


Dependencies
------------

Solidfire Python SDK - solidfire-sdk-python version 1.5.0.87.post1

NetApp Element ansible collections - netapp.elementsw

Example Playbook for creating and configuring an Element cluster
----------------

    ---
    - hosts: localhost
      name: Create and Config HCI Element Cluster [Use-Case 1]
      collections:
        - netapp.elementsw
      connection: local
      vars_files:
        - vars.yml
      tasks:
        - name: Create HCI Element cluster
          include: tasks/create_cluster.yml
        - name: Delay
          pause:
            minutes: 4
        - name: Add drives to cluster
          include: tasks/add_drives.yml
        - name: Config the HCI Element cluster
          include: tasks/config_cluster.yml
        - name: Configure a vlan network
          include: tasks/create_vlan.yml

Example Inventory File  
----------------------

    [elementsw]
    x.x.x.x

Example Command to run the playbook
----------------

    ansible-playbook -i hosts playbook.yml -u element_username -k

Author Information
------------------

- [Nikhil M Kulkarni](nikhil.kulkarni@netapp.com) - NetApp Solutions Automation Team

