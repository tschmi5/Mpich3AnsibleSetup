# Mpich3 Distrubed Computing Raspberry Pi Cluster

Ansible Playbooks to build a cluster of Pi's that run using Mpich3 for distributed computing

Prereqs: 
- A set of fresh raspberry pi's
- Ansible installed on a host (I used 2.9.16)
- From you ansible host copy your pubkey to all Pi's
- A host file with the following style
  ```
  [master]
  192.168.1.10 hostname=master

  [workers]
  192.168.1.11 hostname=node1
  192.168.1.12 hostname=node2
  192.168.1.13 hostname=node3
  192.168.1.14 hostname=node4
```

Use your fastest Machine as master. Building Mpich3 takes a while so it is only built on master and then copied to the workers

To Run:
```
ansible-playbook -u pi -i hostsfile Main.yml
```