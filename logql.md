# geomap

## geo ip

```
sum by (country_code) (count_over_time({unifi="yes"} | json | label_format country_code=geoip_country_iso_code | firewall_interface="WAN_LOCAL" | firewall_rule_action="D" | __error__="" [$__interval] ))
```

# more fields
```
**sum by (country_code) (count_over_time({unifi="yes"} | json | label_format country_code=geoip_country_iso_code | label_format latitude=geoip_latitude | label_format longitude=geoip_longitude | firewall_interface="WAN_LOCAL" | firewall_rule_action="D" | __error__="" [$__interval] ))**
```

"expr": "sum by (iso_code) (count_over_time({container=\"geologger\",namespace=\"traefik-system\",stream=\"stdout\"} \n  | json iso_code=\"geolocation.country.iso_code\", \n         requesthost=\"RequestHost\", \n         privateClientAddress=\"privateClientAddress\" \n  | privateClientAddress=\"false\" \n  | requesthost=~\"$requesthost\" \n  | iso_code!=\"\" [$__interval]))"

```
sum by (geoip_country_iso_code,geoip_country_name,geoip_latitude,geoip_longitude,geoip_country_name,remote_ip,firewall_destination_ip,firewall_spt) (count_over_time({unifi="yes"} | json | firewall_interface="WAN_LOCAL" | firewall_rule_action="D" | __error__="" [$__interval] ))
```

---

```
sum by (geoip_country_iso_code,geoip_country_name,geoip_latitude,geoip_longitude,geoip_country_name,remote_ip,firewall_destination_ip,firewall_spt) (count_over_time({unifi="yes"} | json | firewall_interface="WAN_LOCAL" | firewall_rule_action="D" | __error__="" [$__interval] ))
```


## logging table

`{unifi="yes"} | json | label_format dst_ip=firewall_destination_ip | label_format src_ip=remote_ip | label_format src_port=firewall_spt | label_format dst_port=firewall_dtp | label_format protocol=firewall_nf_protocol | firewall_rule_action="D" | __error__=""`
