**DEVELOPER INSTRUCTIONS:**

- Update dependencies to latest versions
- Customize configuration and Caddyfile parsing
- Update godocs / comments (especially provider name and nuances)
- Update README and remove this section

---

HE module for Caddy
===========================

This package contains a DNS provider module for [Caddy](https://github.com/caddyserver/caddy). It can be used to manage DNS records with Hurricane Electric.

## Caddy module name

```
dns.providers.he
```

## Config examples

To use this module for the ACME DNS challenge, [configure the ACME issuer in your Caddy JSON](https://caddyserver.com/docs/json/apps/tls/automation/policies/issuer/acme/) like so:

```json
{
	"module": "acme",
	"challenges": {
		"dns": {
			"provider": {
				"name": "provider_name",
				"api_token": "YOUR_PROVIDER_API_TOKEN"
			}
		}
	}
}
```

or with the Caddyfile:

```
# globally
{
	acme_dns provider_name ...
}
```

```
# one site
tls {
	dns provider_name ...
}
```
