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

# copy paste the tor-snowflake service.conf from this repo
this conf serves snowbridging with tor services only

for proxy standalone:
cd snowflake/proxy
go build
and then
# copy paste the tor-snowflake-proxy service.conf from this repo
this conf serves to load in proxy bridges no tor required for this but remember to copy the directory and specifiy where it located same applies to all conf

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
