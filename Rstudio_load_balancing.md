# Load balancing Configuration

- Load balancing server Master : NCIENAPP30
- Load balancing backup server : NCIENAPP21


## Load balancing server installation.

- Install rstudio in the new server same as the production servers.
- Open ``` /root/rstudio_files/scripts/pam_script_auth ```, and inside the slave array condition add all of the slave nodes.
- Open ``` /etc/rstudio/load-balancer ``` and add slave servers in the respective oreder. This should be done in all the servers.
- Then go to ``` /root/rstudio_files/scripts```, inside that pam_script_auth_nfs_from_app30 , this script was not executable. Made it executable by chmod a+x.
- Login as root in NCIENAPP24 and uncommand the production server hostnames then restart nginx server. ``` /etc/nginx/nginx.conf ``` 
- Then restart RStudio and make online.
- To check the ip of which the session is loaded, open the executable  file in ``` /usr/lib/rstudio-server/bin ``` and do ``` ./rserver-balancer ```
- Done.!
