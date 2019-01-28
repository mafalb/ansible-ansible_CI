# An ansible role for setting up a node for ansible role CI [![Build Status](https://travis-ci.com/mafalb/ansible-ansible_ci.svg?branch=master)](https://travis-ci.com/mafalb/ansible-ansible_ci)

## Basic Usage

```
- hosts: localhost
  roles:
    - role: ansible_ci
    - role: ansible_ci/node/docker
      container_name: centos_testnode1
      volumes:
        - /sys/fs/cgroup:/sys/fs/cgroup:ro
      image_name: centos_image1
      src: centos-7
      recreate: true

- hosts: centos_testnode1
  tasks:
    - name: whatever you want to test
      assert:
        that:
          - ansible_distribution == 'CentOS'
```
Set up the testenvironment.
Does create a docker container and put it into the inventory.
Run tests against the testnode

## License

GPLv3

