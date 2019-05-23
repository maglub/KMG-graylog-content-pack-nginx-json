# Introduction

KMG-graylog-content-pack-nginx-json

Graylog content pack for json based nginx logs

# Installation

The default port numbers for the Graylog inputs are:

* nginx access log: 11525
* nginx error log: 11526

# nginx configuration

Add the following line to your /etc/nginx/nginx.conf

```
      log_format  graylog2_format  '$remote_addr $host $remote_user [$time_local] "$request" $status $body_bytes_sent "$http_referer" "$http_user_agent" "$http_x_forwarded_for" <msec=$msec|connection=$connection|connection_requests=$connection_requests|millis=$request_time>';
```

Add the following lines to your nginx site configuration:

```
  access_log syslog:server=your.graylog.server:11525 graylog2_json;
  error_log syslog:server=your.graylog.server:11526;
```

# References


