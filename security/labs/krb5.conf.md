[libdefaults]
default_realm = LIVNIGUY.COM
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 86400
renew_lifetime = 604800
forwardable = true
default_tgs_enctypes = aes256-cts aes128-cts
default_tkt_enctypes = aes256-cts aes128-cts
permitted_enctypes = aes256-cts aes128-cts
udp_preference_limit = 1
kdc_timeout = 3000
[realms]
LIVNIGUY.COM = {
kdc = 172.31.26.225
admin_server = 172.31.26.225
}
[domain_realm]
