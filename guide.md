---
title: RStudio Administration
---


# RStudio Update Procedures

## Follow the steps

- Stop RStudio --> ``` rstudio-server stop ```
- Download latest RStudio server edition from RStudio web site --> ``` wget <download_URL> ```
- Update using yum --> ``` yum update <Downloaded file> ```
- Restart RStudio --> ``` rstudio-server restart ```


## Example

1. ``` rstudio-server stop ```
1. ``` wget https://download2.rstudio.org/rstudio-server-rhel-1.1.463-x86_64.rpm ```
1. ``` yum update rstudio-server-rhel-1.1.463-x86_64.rpm ```
1. ``` rstudio-server restart ```



# Restarting RStudio and Server.

## Procedure for restarting RStudio.

- Notify about the restart in MS Teams
- Set RStudio offline --> ``` rstudio-server offline ```
- Stop RStudio --> ``` rstudio-server stop ```
- Restart RStudio --> ``` rstudio-server restart ```
