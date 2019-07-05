ansible-role-efs-lightsail
=========

Mount Amazon EFS file systems to VPC Peering Lightsail instances.

Galaxy link
------------

https://galaxy.ansible.com/kaihei777/ansible_role_efs_lightsail/

Requirements
------------

Amazon AWS account, EFS filesystem(s) and VPC Peering Lightsail  virtual server(s) with RedHat.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):


Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
      - {
          role: kaihei777.ansible_role_efs_lightsail,
          mount_type: "vpc-peering",
          aws_efs_paths:
            [
              {
                path: "/mnt/efs",
                owner: "root",
                group: "root",
                mode: "0644",
                region: "ap-northeast-1",
                filesystem_id: "fs-xxxxx",
                mount_target_ip: "172.31.xx.xx",
                state: "mounted",
                opts: "nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2",
              },
            ],
        }

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2019 by Kaihei Sameshima.