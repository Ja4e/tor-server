# tor-server
hosting tor server

make sure you have installed tor

git clone https://gitlab.torproject.org/tpo/anti-censorship/pluggable-transports/snowflake.git
cd snowflake/server
normally you run this with
tor -f torrc

but we have a different approach
we load it under systemctl instead

save it as /etc/systemd/system/tor-snowflake.service

copy paste the tor-snowflake service.conf from this repo

sudo systemctl enable --now tor-snowflake.service/etc/systemd/system/tor-snowflake.service

have fun
