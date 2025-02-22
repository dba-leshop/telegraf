# Netstat Input Plugin

This plugin collects TCP connections state and UDP socket counts by using
`lsof`.

## Global configuration options <!-- @/docs/includes/plugin_config.md -->

In addition to the plugin-specific configuration settings, plugins support
additional global and plugin configuration settings. These settings are used to
modify metrics, tags, and field or create aliases and configure ordering, etc.
See the [CONFIGURATION.md][CONFIGURATION.md] for more details.

[CONFIGURATION.md]: ../../../docs/CONFIGURATION.md

## Configuration

``` toml
# Read TCP metrics such as established, time wait and sockets counts.
[[inputs.netstat]]
  # no configuration
```

## Metrics

Supported TCP Connection states are follows.

- established
- syn_sent
- syn_recv
- fin_wait1
- fin_wait2
- time_wait
- close
- close_wait
- last_ack
- listen
- closing
- none

## TCP Connection State measurements

Meta:

- units: counts

Measurement names:

- tcp_established
- tcp_syn_sent
- tcp_syn_recv
- tcp_fin_wait1
- tcp_fin_wait2
- tcp_time_wait
- tcp_close
- tcp_close_wait
- tcp_last_ack
- tcp_listen
- tcp_closing
- tcp_none

If there are no connection on the state, the metric is not counted.

## UDP socket counts measurements

Meta:

- units: counts

Measurement names:

- udp_socket
