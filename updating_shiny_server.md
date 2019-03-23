# Installing or upgrading shiny server


## This document describes how to install or update shiny server. Our shiny server is NCIENDEVAPP03.

- Step 1: Stop the shiny server  ``` systemctl stop shiny-server.service ```
- Step 2 : Download latest rpm package from shiny site ``` wget https://download3.rstudio.org/centos6.3/x86_64/shiny-server-1.5.9.923-x86_64.rpm ```
- Step 3: Install downloaded rpm package with yum. ``` yum install --nogpgcheck shiny-server-1.5.9.923-x86_64.rpm ```
- Step 4: Restart the shiny server. ``` systemctl restart shiny-server.service ```

- Note:-  For upgrading shiny server the same steps we have to follow, all the settings and configurations will remain same.

