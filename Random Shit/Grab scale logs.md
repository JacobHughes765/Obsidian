ssh spadmin@10.1.2.100 
cd src/prod-ui-v2/logs 
tail -10000 sidekiq.log | grep -A 3 "M207"