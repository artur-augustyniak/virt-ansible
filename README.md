Przykłady użycia Ansible
========================
```
root@ansible ~# cat /etc/ansible/hosts
# Ansible hosts
# See /etc/ansible/hosts.example or
# the on-line documentation at http://docs.ansible.com/intro_inventory.html
# for information on how to configure this file.

ansible               ansible_connection=local

[tomcatservers]
tomcat.virt.lan

[lampservers]
intravel.virt.lan

[dbservers]
mysql-master.virt.lan
root@ansible ~# ansible all -m ping
ansible | success >> {                                                                                                                                                                                                                                                                       
    "changed": false,                                                                                                                                                                                                                                                                        
    "ping": "pong"                                                                                                                                                                                                                                                                           
}                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                             
mysql-master.virt.lan | success >> {                                                                                                                                                                                                                                                       
    "changed": false,                                                                                                                                                                                                                                                                        
    "ping": "pong"                                                                                                                                                                                                                                                                           
}                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                             
intravel.virt.lan | success >> {                                                                                                                                                                                                                                                           
    "changed": false,                                                                                                                                                                                                                                                                        
    "ping": "pong"                                                                                                                                                                                                                                                                           
}                                                                                                                                                                                                                                                                                            
                                                                                                                                                                                                                                                                                             
tomcat.virt.lan | success >> {                                                                                                                                                                                                                                                             
    "changed": false,                                                                                                                                                                                                                                                                        
    "ping": "pong"                                                                                                                                                                                                                                                                           
}                                                                                                                                                                                                                                                                                            
```

Na grupach
----------------------
```
ansible all -m '/bin/echo dfg'
ansible dbservers -a "uname -a" -i -f 3    
ansible-playbook -i inventory zabbix_agent/zabbix_agent.yml -f 2
```

UWAGA! - grupa zdefiniowana w playbooku
----------------------------------------
```
ansible-playbook playbooks/linux_update.yml -f 4
```