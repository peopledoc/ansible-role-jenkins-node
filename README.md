novafloss.jenkins_node
======================

Provision Jenkins SSH slave.


Requirements
------------

python-jenkins from Openstack project to query Jenkins API.


Role Variables
--------------

    # Jenkins node vars.
    jenkins_master: https://jenkins.lan/
    jenkins_node_executors: 2
    jenkins_node_labels: [label1, label2]
    jenkins_node_name: {{ ansible_hostname }}
    jenkins_node_credentials: master-ssh
    # UNIX user vars
    jenkins_username: jenkin
    jenkins_authorized_key: ssh-rsa AAAA...TBZUI9 jenkins@jenkins.lan


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: slave
      roles:
         - role: novafloss.jenkins_node
           jenkins_master: https://jenkins.mycompany.com/


Copyright
---------

Licensed under BSD by @PeopleDoc and contributors.
