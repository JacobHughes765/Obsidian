Login to the firewall and click the "_>" button on the top right, Then follow the steps below 

- Enable Debugging:Access the FortiGate's command-line interface (CLI) and run the following commands to enable debugging for the email system:
    
    - `diag debug reset`
    - `diag debug enable`- `diag debug console timestamp enable`- `diag debug application alertmail -1`