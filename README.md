ansible-role-efs-lightsail
=========

Mount Amazon EFS file systems to VPC Peering Lightsail instances.

Requirements
------------

Amazon AWS account, EFS filesystem(s) and VPC Peering Lightsail  virtual server(s) with RedHat.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    aws_efs_paths:
    - { path: "/some/path", owner: "root", group: "root", mode: "0644", region: "eu-west-1", filesystem_id: "fs-someid", state: "mounted", opts: "nfsvers=4.1"}
    - { path: "/some/other/path", owner: "root", group: "root", mode: "0755", region: "eu-west-1", filesystem_id: "fs-someotherid", state: "mounted", opts: "nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2"}

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: kaihei777.efs-lightsail, x: 42 }

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2019 by Kaihei Sameshima.