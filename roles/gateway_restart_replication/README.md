# Description
This role will restart replication on a previously replicating cluster.
This role requires root access to call create_user.sh and restart_replication.sh which come with gateway version 10 default image.

### Requirements
- The role must be executed with the Ansible user having root privilege.
   root access to run /opt/SecureSpan/Appliance/bin/restart_replication.sh and create_user.sh
   root access to update /etc/my.cnf
-  The network of the target gateways must be pre-configured.
-  The MySQL 8 server must be started

### Dependencies:
There are no dependencies upon other roles.

### Sample Usage
Modify the hosts file under `gateway`
  - define a primary gateway in gateway_primary_db group
  - define a failover gateway in gateway_failover_db group
  
` ansible-playbook gateway-restart-replication.yml -i hosts.yml `
