This repository is an [ansible](http://ansibleworks.com) role for installing a service managed by the supervisor daemon, with a focus on being simple & usable without root.

It depends on the [supervisor](https://github.com/eggsby/ansible-supervisor) role to ensure that supervisord is installed and running.

## Installation:
After you have installed the supervisor role, install this role the same way :)

    cd my-roles-repository
    git clone https://github.com/eggsby/ansible-supervisor supervisor/
    git clone https://github.com/eggsby/ansible-supervise supervise/

## Usage:

    roles:
      - role: supervise
        name: webserver
        command: python -m SimpleHTTPServer
        directory: ~/public/

This would install and start a supervisor program named 'webserver', with a simple config.

see [defaults](https://github.com/eggsby/ansible-supervisor/blob/master/defaults/main.yaml) for supported parameters and the [example project](https://github.com/eggsby/ansible-supervisor-example) for help getting started.
