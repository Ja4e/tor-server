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

edit this:

[Unit]
Description=Tor Snowflake Server
After=network.target

[Service]
Type=simple
User=jake
WorkingDirectory=/home/<user>/snowflake/server
ExecStart=/usr/bin/tor -f /home/<user>/snowflake/server/torrc
Restart=on-failure

[Install]
WantedBy=multi-user.target

sudo systemctl enable --now tor-snowflake.service/etc/systemd/system/tor-snowflake.service

have fun
