Metaname module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with Metaname.

## Caddy module name

```
dns.providers.metaname
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "metaname",
				"api_key": "YOUR_API_KEY",
				"account_reference": "YOUR_ACCOUNT_REFERENCE"
			}
		}
	}
}
```

or with the Caddyfile like:

```
# globally
{
	acme_dns metaname YOUR_ACCOUNT_REFERENCE YOUR_API_KEY
}
```
or
```
# one site
tls {
	dns metaname {env.metaname_ref} {env.metaname_key}
}
```
