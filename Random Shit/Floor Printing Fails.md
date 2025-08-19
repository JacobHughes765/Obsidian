

If the floor suddenly and comprehensively loses the ability to print, check Sidekick at [http://prodsvr2/sidekiq/queues](http://prodsvr2/sidekiq/queues) and check for a large amount of enqued jobs.  Make sure ProdUI server 10.1.2.100 is running fine in vSphere. 

Per Kevin: 

i just put a script in the home folder of the spadmin user on the spwebapps5 (10.1.2.100) server, called restart-stack.sh   Run the script in order to restart the qued services.  

When running the command on spwebapps5 run  

./restart-stack.sh prod-ui-v2 

It can be used for x2.. 

./restart-stack.sh x2
