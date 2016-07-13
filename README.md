# Ansible Role: Memcached

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-memcached.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-memcached)

An Ansible Role that installs Memcached on RedHat/CentOS or Debian/Ubuntu Linux.

## Requirements

None.
## Installation
Role support installation in both versions of packages: `.rpm` and `.deb` .
To install Memcached from package manager (yum or apt) modify variable:

    memcached_use_pkg_mgr: true

If variable is set to false ansible role will download `.rpm` or `.deb` package from given url and install from it.

    memcached_pkg_src_url:

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    memcached_user: memcached

The user under which the Memcached daemon will run.

    memcached_port: 11211
    memcached_listen_ip: 127.0.0.1

The port and IP address (127.0.0.1 for localhost) on which Memcached will listen for requests.

    memcached_memory_limit: 64
    memcached_connections: 1024

Memcached limits. The maximum amount of RAM `memcached` will consume (64MB is the default), and the maximum number of simultaneous connections memcached will handle.

    memcached_log_file: /var/log/memcached.log

The location of the memcached log file.

    memcached_log_verbosity: ""

Normally memcached does not log anything. Change to "-v" to enable logging or to "-vv" for debug logging.


## Optional
- run_mode: One of Deploy, Stop, Install, Start, or Use. The default is Deploy which will do Install, Configure, then Start.
- memcached_iptables_nodes: List of ip addresss that will have access do Memcached.

## Dependencies

None.

## Example Playbook

    - hosts: cache
      roles:
        - { role: geerlingguy.memcached }

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
