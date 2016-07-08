# Vagrant Ubuntu16.04
Ubuntu 16.04 with vagrant.

vbox: [ubuntu/xenial64](https://atlas.hashicorp.com/ubuntu/boxes/xenial64)

## required
- Vagrant    (>= 1.7)
- Virtualbox (>= 5)
- Ansible    (>= 1.9)

## Installation
```sh
$ git clone git@github.com:igrs/vagrant-ubuntu1604.git
$ cd vagrant-ubuntu1604
$ vagrant up
```

## Provisioned
- Erlang-OTP (default: 19.0)
- Elixir     (default: 1.3.1)
- PostgreSql (default: 9.5)
- Ruby       (default: 2.3.1)
- Node.js    (default: 6.3.0)
- Certbot    (from github.com to /home/ubuntu/)

You can change version at ansible vars.

## LICENSE
Free for use or fork.
