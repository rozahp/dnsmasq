# dnsmasq-patch

Dnsmasq patch with options for filtering IPv6, HTTPS-query and unknown query types.

## AUTHOR

Phazor / Cascade 1733

## LICENSE

Please feel free to copy, distribute and change this program in any way you like.

## dnsmasq-2.82-filter-aaaa+https+unknown.patch

This patch adds the following configuration options:

- filter-aaaa:      filter all ipv6 queries
- filter-https:     filter all https / query type 65 
- filter-unknown:   filter all unknown query types (except https)

Further changes as well:

- increase ttl-floor-limit to 604800 (--min-cache-ttl)
- increase dnssec-min-ttl to 3600 (DNSKEY and DS records in cache last at least this long)
- conntrack
- dnssec
- no dumpfile
- no dhcp6

### Apply patch

1) git clone git://thekelleys.org.uk/dnsmasq.git (version 2.82)

2) cd dnsmasq

3) git apply dnsmasq-2.82-filter-aaaa+https+unknown.patch

4) make

5) cp src/dnsmaq to your server

6) Add following options to your dnsmasq.conf:
    
    - filter-aaaa
    - filter-https
    - filter-unknown

7) Enjoy the silence!

## Inspiration

Got inspiration from other coders and patches online.

## TODO

* ?
