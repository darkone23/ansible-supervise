This repository is an [ansible](http://ansibleworks.com) role for installing a service managed by the supervisor daemon, with a focus on being simple & usable without root.

It depends on the [supervisor](https://github.com/eggsby/ansible-supervisor) role to ensure that supervisord is installed and running.

## Installation:
See [galaxy](https://galaxy.ansibleworks.com)

    ansible-galaxy install eggsby.supervisor eggsby.supervise

## Usage:

    roles:
      - role: eggsby.supervise
        name: webserver
        command: python -m SimpleHTTPServer
        directory: ~/public/

This would install and start a supervisor program named 'webserver', with a simple config.

see [defaults](https://github.com/eggsby/ansible-supervisor/blob/master/defaults/main.yaml) for supported parameters and the [example project](https://github.com/eggsby/ansible-supervisor-example) for help getting started.
