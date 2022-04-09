```
root@de79f6364b72:/log/client_logs/setup.ubnt.com# grep 'WAN_LOCAL' messages.log

cd /log/client_logs/setup.ubnt.com

grep 'WAN_LOCAL' /log/client_logs/setup.ubnt.com/messages.log | head -1 | promtail --stdin --dry-run --inspect --config.file=/etc/promtail/promtail-debug.yaml -server.http-listen-port 9081 --log.level debug

echo '2022-04-09T01:55:52.6930548+0000{__path__="/log/client_logs/*/messages.log", job="rsyslogng", miner="boss-monitor"}     Mar 22 00:25:10 ubnt kernel: [WAN_LOCAL-4000-D]IN=eth2 OUT= MAC=80:2a:a8:00:11:33:00:11:22:33:44:66:08:00 SRC=54.230.162.3 DST=192.168.0.11 LEN=91 TOS=0x00 PREC=0x00 TTL=231 ID=53349 PROTO=TCP SPT=443 DPT=58568 WINDOW=138 RES=0x00 ACK PSH URGP=0' | promtail --stdin --dry-run --inspect --config.file=/etc/promtail/promtail-debug.yaml -server.http-listen-port 9081 --log.level debug
```
