vol_snapshot_schedule
-----------

This use-case can be used to create volume snapshots and snapshot schedules.

Usage
----

1. Define the details of snapshots to be created in vars/main.yml file
2. Define the details of snapshot schedules to be created in vars/main.yml file
3. Define the cluster MVIP in hosts file
4. Run the playbook using - ansible-playbook create_volume_snapshot_schedule_playbook.yml -i hosts -u <<elementsw_username>> -k
5. Verify that the intended snapshots or snapshot schedules are created in the Element GUI
