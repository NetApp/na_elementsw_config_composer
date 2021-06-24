config_logical_storage
-----------

This use-case can be used to configure the accounts, qos policies, volumes, initiators and access groups used for managing logical storage through NetApp Element.

Usage
----

1. Define the details of accounts, qos_policies, volumes, initiators, access groups in vars/main.yml variable file
2. Define Element cluster MVIP in hosts file
3. Run the playbook using - anisble-playbook config_logical_storage_playbook.yml -i hosts -u <<username>> -k
4. When prompted, enter the password for Element
5. Once the playbook runs successfully, verify that the intended logical constructs are created in the Element GUI

