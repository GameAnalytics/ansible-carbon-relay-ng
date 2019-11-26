[![Build Status](https://travis-ci.com/GameAnalytics/ansible-carbon-relay-ng.svg?token=psJ7kzCPVMkCYuYpVEsy&branch=master)](https://travis-ci.com/GameAnalytics/ansible-carbon-relay-ng)
# carbon-relay-ng Ansible role

This role aims to configure and start carbon-relay-ng on target machine running under Supervisor

For an example Playbook, see `test/main.yml`

Requirements
------------
The role requires Supervisor to be installed in the target machine.

Role Variables
--------------

**Required**

`graphite_addr`: The URL to send metrics to.

`graphite_apikey`: The API key to the hosted Graphite service

**Optional**

`carbon_relay_ng_port`: The service listens on this port. Default: 2003

`carbon_relay_ng_bind`: IP address where the service binds to. Default: localhost

`graphite_route_key`: carbon-relay-ng route key: Default: 'grafanaNet'

`graphite_route_type`: carbon_relay_ng route type: Default: 'grafanaNet'

`graphite_interval`: Period of metric sending by your application: Default: '1m'

`graphite_interval_ms`: Must equal to `graphite_interval` but in ms. Default: 60000

`wait_for_healthcheck`: Whether to wait for carbon-relay-ng to listen on port as a part of the role run. Default: `True`

Test
--------------
In order to run tests locally:
```
$ ansible-playbook -i test/inventory test/main.yml -vvv
```

You need Docker and also `docker-py` library.

See [here](https://www.ansible.com/blog/testing-ansible-roles-with-docker) for more info about Ansible role testing

Note that there are problems with Ansible/pip/docker-py. See [here](https://medium.com/dronzebot/ansible-and-docker-py-path-issues-and-resolving-them-e3834d5bb79a)

Best practices
--------------
For Ansible best practices, please read [here](http://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html) and specially [here](https://github.com/enginyoyen/ansible-best-practises).

