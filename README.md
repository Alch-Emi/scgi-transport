SCGI reverse proxy transport module for Caddy
===============================================

This plugin adds SCGI reverse proxying support to Caddy.

The `scgi` transport module is based on the `fastcgi` transport module available.


SCGI Directive
-----------------------------------------------
To use the `scgi` directive, it must first be added under caddy's global setting:
```
{
  order   scgi after php_fastcgi
}
```

### Syntax ###
```
scgi [<matcher>] <gateways...> {
	env [<key> <value>]
	dial_timeout  <duration>
	read_timeout  <duration>
	write_timeout <duration>

	<any other reverse_proxy subdirectives...>
}
```

Reverse Proxy
-----------------------------------------------
The `scgi` transport may also be specified under the `reverse_proxy` handler.

### Expanded Form ###
```
route {
  reverse_proxy [<matcher>] <gateway> {
    transport scgi {
      ...
    }
  }
} 
```
