# Introduction

This code is prepared for automatic installation of Prometheus. No matter how many exporters you have, it will be automatically added to the monitoring list after starting the prometheus service. Although service discovery helps us a lot in prometheus automation, this can be another way for prometheus automation.

# Prerequirements
first of all you need to clone the project and  gunzip the following files:
```
gunzip roles/exporters/tasks/node_exporter.gz
gunzip roles/prometheus-server/tasks/prometheus.gz
gunzip roles/prometheus-server/tasks/promtool.gz
```
You need to install Ansible to run this code. Then edit the /etc/ansible/hosts file to the following format.\
```
[exporters]
EXPORTER_IP_ADDRESS

[prometheus-server]
SERVER_IP_ADDRESS 
```

Also, you have to enable ssh on the side of the clients that you want to act as exporters:
ssh-copy-id USERNAME@EXPORTER_IP_ADDRESS
# Run the code
Now go to the main folder and run the following command to run the code.
```
ansible-playbook app-setup-yml
```
