# Storm-UI-Issue-
To resolve storm ui issue in windows. 


Steps to Solve 

STEP 1:
Firefox: Goto about:config and search for network.negotiate-auth.trusted-uris double-click to add value 
"http://storm-ui-hostname:8080 <http://storm-ui-hostname:8080/> " 
http://HOSTNAME.DOMAIN.net:8744 <http://HOSTNAME.DOMAIN.net:8744/>  

- Google-chrome: start from command line with: 
google-chrome --auth-server-whitelist="storm-ui-hostname" --auth-negotiate-delegate-whitelist="storm-ui-hostname" 
google-chrome --auth-server-whitelist="HOSTNAME.DOMAIN.net" --auth-negotiate-delegate-whitelist="HOSTNAME.DOMAIN.net" 
chrome --auth-server-whitelist="HOSTNAME.DOMAIN.net" --auth-negotiate-delegate-whitelist="HOSTNAME.DOMAIN.net" 


- IE: Configure trusted websites to include "storm-ui-hostname" and allow negotiation for that website 

STEP 2: Add the principal in windows MIT Kerberos 

for kdc:
ksetup /addkdc HADOOP-DQA-CNJ01.DOMAIN.NET HOSTNAME.DOMAIN.net 
for service(storm):
ksetup /addhosttorealmmap HOSTNAME.DOMAIN.net HADOOP-DQA-CNJ01.DOMAIN.NET 

STEP 3:
Add user id (in caps) to ragner.
