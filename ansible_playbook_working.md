# Ansible Playbook Working Notes.
## Documentation on how to work with ansible playbook
-   Ansible server     NCIENDEVAPP01
-   Directory    /etc/ansible/playbooks
-   Host file   /etc/ansible/hosts ( Hosts groups are listed in this file )
-   Working     ansible-playbook < yml_file.yml>

## How to Run a playbook.

-   Open the ‘.yml’ file and edit the ‘hosts’  line ( Need to mention desired hosts, Host list can be found in ‘/etc/ansible/hosts’ file )
-   Run the playbook   ansible-playbook < yml_file.yml> ( after editing the hosts line run that file )

# Details on how each playbook works.

##  flush_ad.yml

-   Used when AD login issue occurs. In most situations monitoring script will push alert in MS Teams.
-   After confirming the AD issue we can run the ‘flush_ad.yml’ playbook.


## change_any_string_for_R_version.yml

-   To find the Rprofile.site files from installed R versions and change any string.

## copy_a_file_from_serverA_serverB.yml

-   To Copy Remote-To-Remote from serverA to server.
-   Need to mention the source host and  destination.

## rstudio_restart.yml

-   Can be use when rstudio down or not reachable.
-   Restart ‘rstudio service’.
-   Mention the host group and run the playbook.

## server_restart.yml
-   Used when servers need to be restarted.
-   It takes all necessary actions include unmounting.
