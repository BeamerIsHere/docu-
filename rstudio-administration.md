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


## Restarting the Node.

- Notify about the restart in MS Teams 
- Stop RStudio as mentioned above. 
- Check all mounted shares --> ``` df -Th ``` 
- unmount all the shares, Eg: --> ``` umount -l /home/NCIWIN ``` ( use -l for force remove ) 
- Reboot the server --> restart ( root access needed )

## Adding PopUp in Rstudio login

- File will be in /etc/rstudio/login.html.
- Add the ollowing lines in the code to make it work.
- <script>
- var today = new Date();
- var dd = today.getDate();
- var mm = today.getMonth()+1; //January is 0!
- var yyyy = today.getFullYear();
- if(dd<10){dd='0'+dd}
- if(mm<10){mm='0'+mm}
- var today = dd+'/'+mm+'/'+yyyy;
- var days = [];
- days = ["Enter the specific days"];
- if (days.indexOf(today, days) > -1) {
- if(confirm("The coRe is putting out a quick 2-question survey to assess interest in various technical trainings (estimated time 2 minutes).\n\n Please click Ok to take the survey. If you have already taken it,click Cancel.")) {
- window.open('https://forms.office.com/Pages/ResponsePage.aspx?id=N6xk27Cc4EitvRJf_0sUUiHL8cBmEvFOmQuZic1uebBUQkxFMFRJTThWUlJXU1pJMkRSSTdEVkRBMC4u', '_blank');
- }}
- </script>

- If the notication should also appear when a user opens a session, please follow the steps below,
- Go to /etc/rstudio/notifications.conf and add the details
- StartTime: 2019-03-07
- EndTime: 2019-03-11
- Message: Please Enter the Message Here.


