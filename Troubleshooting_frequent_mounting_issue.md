# Troubleshooting Frequent Mounting Issue

## Scenario: - User complain about frequent energy share missing.

## Note: - Before starting this troubleshooting user must killed all the sessions. Ansible command must run from NCIENDEV01

- Step 1: Find in which server energy share is missing, normally log-in to the servers and check the mount
			
				```					df -Th | grep <user>
											OR
					ansible rstudio_pro -a "df -h" | grep -e nyu -e CHANGED	
																			```
					
- Step 2: We’ll get to know that anyone of the server missing the energy share. 
  Then we need to confirm if the user has any running process. In most cases user will have zombie process running. 
  
				``` 				ps -ef | grep <user> 
				
											OR
											
				    ansible rstudio_pro -a "ps -ef "| grep -e nyu -e CHANGED 
																			```
					
- Step 3: Now we must kill this unwanted zombie process. Checking the process tree might help.
				
				``` 				pstree -p <PID>							```
				
- Step 4 : Kill the zombie process, It may work at first time try killing the related process as well.
				
				```					Kill -9 <PID>							```

- Step 5: After killing the process remount the share, using “rsessioncleaner” or manually.
					
					
## Alternative method.
	
- Other Method to verify this is check the directories in user’s home. And check the permissions if you are getting this error unmount the drive. 
  After that check if the directory permissions are back.
  
  
				```					cd /home/NCIWIN/nyu/energy
									[root@ncienapp16 nyu]# ll
									ls: cannot access energy: Permission denied
									total 792
									d????????? ???  ???? 			?? ??   energy 
															
																				``` 
																				
- Unmount the  directory and remount again, check whether drive is mounted or not.

				```					unmount -l /home/NCIWIN/nyu/energy 
									mount /home/NCIWIN/nyu/energy
									
																				```
																				
																				
						
				
											
					
