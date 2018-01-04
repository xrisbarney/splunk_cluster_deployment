

# Splunk Spaceballs
## Indexer Cluster & Search Head Cluster

![spaceballs](spaceballs.gif)
*May the Shwartz be with you!*

### based on https://github.com/cuddlesec/ansible-splunk-simple
### also based on Bash-driven setup:   https://github.com/aplura/Vagrant_Splunk_Cluster

Ansible-based Splunk Cluster creator

Tested on Centos 7 x64

These playbooks create 2 Clusters (SH and Indexer) in addition to creating a Splunk Indexer Master and a Splunk SearchHead Deployer. 

They also add Search Heads as search peers on the Indexer cluster

The end result is this:
![chart](Splunk_cluster.png)

---
### Run in following order:
1. update Hosts file with Search Head and Cluster Master, update Deployer and Master IPs
1. update config.yaml file for correct splunk version, passwords, IPs, etc
  
1. run LUDICROUS SPEED to install master, indexers, deployer, search heads 
    ```bash 
    ansible-playbook -i hosts play_ludicrous_speed.yaml -v
    ```

Login to Master < masterIP >:8000 and click Settings > Indexer clustering to see the clusters at work.
