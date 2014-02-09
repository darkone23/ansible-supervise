This repository is an [ansible](http://ansibleworks.com) role for installing a service managed by the supervisor daemon, with a focus on being simple & usable without root.

It depends on the [supervisor](https://github.com/eggsby/ansible-supervisor) role to ensure that supervisord is installed and running.

The only hard dependency on the target machine is `virtualenv`. This makes it so we can install supervisord without root.

## Installation:
See [galaxy](https://galaxy.ansibleworks.com)

    mkdir -p roles
    ansible-galaxy install eggsby.supervise -p roles

## Usage:

    hosts: all
    roles:
      - role: eggsby.supervise
        name: webserver
        command: python -m SimpleHTTPServer
        directory: ~/public/

This would install and start a supervisor program named 'webserver', with a simple config.

    ~/bin/supervisorctl status
    curl -I localhost:8000

see [defaults](https://github.com/eggsby/ansible-supervisor/blob/master/defaults/main.yaml) for supported parameters and the [example project](https://github.com/eggsby/ansible-supervisor-example) for help getting started.
