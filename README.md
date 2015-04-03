# ansible-test

repository test ansible

playbook de test pour creation d'utilisateur avec:

- une liste général d'utilisateur (group_vars/all or group_vars/[group] or host_vars/[host])
- une liste de type/role contenant les noms des utilisateurs (all:vars or group_vars/all)
- une variable user_list contenant les types de roles à activer sur le host (group_vars/[group] or host_vars/[host]

mysolo@ethoo ~/ansible $ cat local_host1 
[local]
localhost ansible_connection=local ansible_python_interpreter=python2

[all:vars]
#exec_user=["exec_user1","exec_user2"]
exec_user=["exec_user2"]



[local:vars]
user_list=exec_user
mysolo@ethoo ~/ansible $ cat group_vars/local 
---
users:
  exec_user1:
    login: exec_user1
    uid: 2000

  exec_user2:
    login: exec_user2
    uid: 2001
   
  #nombre: 2



group_vars/[group]
exemple:
list de variable definissant les utilisateurs
---
users:
  exec_user1:
    login: exec_user1
    uid: 2000

  exec_user2:
    login: exec_user2
    uid: 2001

