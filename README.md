Elasticsearch role
=========
[![Build Status](https://api.travis-ci.org/skarj/ansible-role-elasticsearch.svg?branch=master)](https://travis-ci.org/skarj/ansible-role-elasticsearch)

Ansible role for [elasticsearch](https://www.elastic.co/products/elasticsearch) 6.x installation.
Versions lower than 6 are not supported by this role.

Requirements
------------

* Ansible 2.5
* This role requires [hash_behaviour=merge](http://docs.ansible.com/ansible/latest/reference_appendices/config.html#default-hash-behaviour) for variables


Dependencies
------------

None


Role Variables
--------------

Default config variables are described in *defaults/main.yml*.
If you need an extended configuration you can specify it in the variables for each environment in section *elasticsearch.config*.
Structure of section *elasticsearch.config* repeats *elasticsearch.yml*, you can insert any parameters described in official elasticsearch [documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/settings.html)

  * _elasticsearch.instance_name_ unique instance name - mandatory variable!

  * _elasticsearch.jvm.heap_size_ heap size of java memory, see about
[setting heap size](https://www.elastic.co/guide/en/elasticsearch/reference/current/heap-size.html)


Example Playbook
----------------

An example of how to use this role:

        - hosts: all
          roles:
            - role: elasticsearch
              elasticsearch:
                instance_name: node1
                jvm:
                  heap_size: 1g
                config:
                  "network.host": "0.0.0.0"
                  "cluster.name": "elasticsearch"


License
-------

MIT


Author Information
------------------

Sergey Baranov <skaarj.sergey@gmail.co>
