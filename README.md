# LXC exporter
[![Build Status](https://travis-ci.org/SebastianCzoch/lxc-exporter.svg?branch=master)](https://travis-ci.org/SebastianCzoch/lxc-exporter) [![Code Climate](https://codeclimate.com/github/SebastianCzoch/lxc-exporter/badges/gpa.svg)](https://codeclimate.com/github/SebastianCzoch/lxc-exporter) [![GoDoc](https://godoc.org/github.com/SebastianCzoch/lxc-exporter?status.svg)](https://godoc.org/github.com/SebastianCzoch/lxc-exporter)  [![License](https://img.shields.io/badge/licence-Apache%20v2-green.svg)](./LICENSE)

LXC exporter is small application written in Go which are providing some metrics about LXC containers running on host in [Prometheus.io](http://prometheus.io) format.
It's beta version, already tested on Ubuntu Willy (15.10) and linux kernel in version 4.x.x.
This application should be installed only on physical machine, not on LXC container. All data is reading from linux `cgroup`.

## Metrics
| Metric name           			| Description                                             					| Enabled by default |
|-----------------------------------|---------------------------------------------------------------------------|--------------------|
| lxc_cpu               			| Seconds the cpus spent in each mode. For all containers 					| yes                |
| lxc_cpu_precentage    			| Precentage of usage processor                           					| yes                |
| lxc_cpu_physical_real 			| Seconds the real physical cpu spent in each mode. (minus containers usage)| yes                |
| lxc_cpu_physical_real_precentage	| Precentage of usage processor (minus containers usage)       				| yes                |
| lxc_memory_usage					| Memory usage in each container in bytes       							| yes                |

## Flags
| Name               	| Description                                 	| Default value 	|
|--------------------	|---------------------------------------------	|---------------	|
| web.listen-address 	| The address to listen on for HTTP requests. 	| :9125         	|

## Building and running

    make
    ./lxc-exporter <flags>

## Running tests

    go test ./...

## License

[Apache v2](./LICENSE)

## Support

Issues for this project should be reported on GitHub issues

Staff responsible for project:

* [Sebastian Czoch <sebastian@czoch.pl>](sebastian@czoch.pl)
