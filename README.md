test_molecule_monorepo
----------------------
Test multiple ansible roles in a repository

Purpose
-------
* Write integration tests for existing Ansible roles using molecule
* Remove duplication in case a set of roles have something in common.

Prerequisites
-------------
Install *podman* (I used a MacBook).

How I did this
--------------

* pip install -r requirements.txt
* molecule init role tme.common_stuff --driver-name podman
* molecule init role tme.specific_stuff --driver-name podman
* molecule init role tme.other_stuff --driver-name podman
* molecule init scenario --driver-name podman default
* molecule init scenario --driver-name podman second_integration

Launch tests
------------

* molecule test -s default
* molecule test -s second_integration
