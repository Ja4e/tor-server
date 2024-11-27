# tor-server

hosting tor servers

make sure you have installed tor

git clone https://gitlab.torproject.org/tpo/anti-censorship/pluggable-transports/snowflake.git
cd snowflake/server
normally you run this with
tor -f torrc

but we have a different approach
we load it under systemctl instead

save it as /etc/systemd/system/tor-snowflake.service

## copy paste the tor-snowflake as service.conf from this repo
this conf serves snowbridging with tor services only

for proxy standalone:
cd snowflake/proxy
go build
and then
## copy paste the tor-snowflake-proxy as service.conf from this repo
this conf serves to load in proxy bridges no tor required for this but remember to copy the directory and specifiy where it located same applies to all conf

### TO make this proxy more effective you might want to port forward 80, 443 and 9001 You willl be expected to to be connected with at least 30 client per hour... Highly dependent to your network bandwidth.

## copy paste the snowflake-broker.service from this repo
Also make sure all these files in that cloned repo has full read and write so your systemctl does not break due to permission denied... 
### have fun dude we will contribute censorship-free society 



if tehres any update
do:
in the snowflake repo
git pull
go build
if you wanted to host proxy as well dont forget to:
cd proxy 
go build

sudo systemctl enable --now tor-snowflake.service/etc/systemd/system/tor-snowflake.service

have fun
