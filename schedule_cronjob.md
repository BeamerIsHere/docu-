#Schedule cronjob

##When a user requests to schedule a new cron job, we need to follow the below procedure.
-  Check whether a service user has been created while asking to put a cron entry.
-  Note that the created user must be a service user. Otherwise the password will get expired for that user as per the policy.
-  Confirm with the user the schedule when, he/she needs to setup the cron activity and the script name.
-  The service user created must be a AD user.
-  Once the username and password is received edit the setting_up_service_account_for_cron.yml and provide the username and password in the below tags.

                                    ```srv_user: "userName"```
                                    ```srv_user_psw:"passwd"```

-  Once edited execute the playbook with as shown below.

				    ```ansible-playbook setting_up_service_account_for_cron.yml```


-  Once the playbook is called, it will mount the cifs energy drive to that particular service user’s home directory.
-  Once executed the playbook go to the cron server(NCIENDEVAPP25), switch as that user and enter the cron job as per the schedule provided.
