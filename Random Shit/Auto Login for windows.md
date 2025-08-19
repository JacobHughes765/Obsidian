
How to Enable AutoLogon for windows computers 

1. Windows Key + R to open run box 
    

2. Type in Regedit and hit ctrl+shift+enter to Run as Admin 
    

3. Navigate to HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon 
    

4. Right click and create new key if these keys are not on the page, if they are right click modify or double left click to pull up a box that shows the value, Enter the value shown below. 
    

DefaultUserName (shopfloor) 

DefaultPassword (pass@word1) 

AutoAdminLogon (1) 

DefaultDomainName (stoneplasticsmfg.com) 

5. Restart Computer to see if the autologon worked 
    

6. If did not autologin when restarted, Double Check your username and password and make sure everything is set as above
   
   
   
   