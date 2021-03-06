fail2ban
=========

Fail2Ban is a program written in Python that aims to detect Brute-Force attacks.
It reads the log files of several servers (SSH, FTP, HTTP, etc.) and studies the unusual behaviors
of repeated authentication failures. It bans the IP address of the client with an iptables rule.
fail2ban is an Ansible role that allows you to install the eponymous program.

Requirements
------------

None.

Role Variables
--------------
| Name	        | Default Value	| Description|
| ------------- |:-------------:| -----------|
|fail2ban_iptables_enabled|False|Booleen to change the configuration of fail2ban if an iptables firewall is enabled on the server.|
|fail2ban_mta_agent|postfix|Mail server to send alerts.|
|fail2ban_init_script|/etc/init.d/fail2ban|Script Bash to control (start, stop, status, etc...) Fail2Ban.|
|fail2ban_config_file|/etc/fail2ban/jail.conf|Fail2Ban configuration file.|
|fail2ban_config_backup_file|/etc/fail2ban/jail.conf.backup|Fail2Ban's original configuration file.|
|fail2ban_alert_mail|root@localhost|Email address for receiving alerts.|
|fail2ban_goss_enabled|False|Enable goss to check fail2ban after installation.|
|fail2ban_sshd_enabled|False|Enable the fail2ban control on the SSH server.|
|fail2ban_sshd_maxretry|6|Number of authentication failed to ban a client.|
|fail2ban_sshd_bantime|600 seconds (10 minutes)|Exclusion time.|
|fail2ban_proftpd_enabled|False|Enable the fail2ban control on the ProFTP server.|
|fail2ban_proftpd_maxretry|6|Number of authentication failed to ban a client.|
|fail2ban_proftpd_bantime|600 seconds (10 minutes)|Exclusion time.|

------------

None.

Example Playbook
----------------

Install fail2ban
```yaml
- hosts: all
  roles:
    - { role: fail2ban }
```

License
-------

BSD

Author Information
------------------

Eric LEGBA.