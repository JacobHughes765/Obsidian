sudo openfortivpn -c /etc/openfortivpn/config -o "Token"

Where the "Token" is you have to go onto your fortitoken and get the token from there and put it in, Don't add the "".

In the  Directory /etc/openfortivpn/ you want to edit the config to look like this

![[Pasted image 20250916135317.png]]
No password in the config, no password on the cli, it will ask you for the password which will be your password to login..
