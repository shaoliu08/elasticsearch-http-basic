# HTTP Basic auth for ElasticSearch

This plugin provides an extension of ElasticSearchs HTTP Transport module to enable HTTP Basic authorization.

## Installation

Copy `elasticsearch-http-basic-<version>.jar` to `plugins/http-basic`. Or use `bin/plugin` to do so.
    
## Configuration

The plugin is disabled by default. Enabling basic authorization will disable the default HTTP Transport module.

```
http.basic.enabled = true
http.basic.user = "my_username"
http.basic.password = "my_password"
```

Be aware that the password is stored in plain text.

## Testing

```
$ curl -v --user my_username:my_password localhost:9200 # works
$ curl -v --user my_username:password localhost:9200 # sends 403
```