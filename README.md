# Homelab

Documentation and automation of my homelab setup. Mostly to remind myself of what I've done, but maybe someone else can make use of it.

Currently work in progress to move all documentation and configuration to this repository.

## Background

The purpose of my homelab environment is to have a playground evaluate and run the technologies I'm interested in.

My aim is to:

* have all parts documented
* ease reuse between hardware and sites
* automated as much as possible
* infrastructure as code
* testable infrastructure
* crucial parts with low downtime

... but not to:

* replace usage of public cloud services
* have high availability

## Main technologies

* [Ansible](https://www.ansible.com/)
* [Xen](https://www.xenproject.org/) for virtualization
* [Alpine Linux](https://alpinelinux.org/) for bare metal machines and single-purpose VMs - diskless setups preferred
* [CoreOS Container Linux](https://coreos.com/os/docs/latest/) for Kubernetes VMs
* [Kubernetes](https://kubernetes.io/) for most services
* [ZFS](http://open-zfs.org/wiki/Main_Page) for all persistent storage

## Site example

Hardware:

* Switches with SNMP and VLAN support
* Router (NAT, firewall, ...) - e.g. [PC Engines apu2c2](https://www.pcengines.ch/apu2c2.htm)
* One or many machines running Kubernetes in one way
* [Ubiquiti UniFi](https://www.ubnt.com/unifi/unifi-ap/) WiFi access points

Software:

* Machines running Xen and Alpine Linux
* Networking driver domain  with Alpine Linux
* Storage driver domain with Debian Linux and [ZFS on Linux](http://zfsonlinux.org/)
* VMs running CoreOS and Kubernetes