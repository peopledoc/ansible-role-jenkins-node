novafloss.jenkins-node
======================

Provision Jenkins SSH slave.


Requirements
------------

- `novafloss.jenkins-api`: to create the node with the jenkins REST API


Role Variables
--------------

    # UNIX user vars
    jenkins_authorized_key: ssh-rsa AAAA...TBZUI9 jenkins@jenkins.lan
    jenkins_home: /var/lib/jenkins
    jenkins_username: jenkins

    # Jenkins node vars
    jenkins_master_url: https://jenkins.mycompany.com/
    jenkins_node_executors: 2
    jenkins_node_host: jenkins-node-1.lan.mycompany.net (default: {{ ansible_eth0.ipv4.address }})
    jenkins_node_port: 22
    jenkins_node_labels: [label1, label2]
    jenkins_node_name: jenkins-node-1 (default: {{ ansible_hostname }})
    jenkins_node_credentials_id: master-ssh


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: slave
      roles:
        - role: novafloss.jenkins-api
        - role: novafloss.jenkins-node
          jenkins_authorized_key: ssh-rsa AAAA...TBZUI9 jenkins@jenkins.lan
          jenkins_master_url: https://jenkins.mycompany.com/
          jenkins_node_credentials_id: master-ssh


Copyright
---------

Licensed under BSD by @PeopleDoc and contributors.
