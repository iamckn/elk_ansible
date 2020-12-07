# elk_ansible
Ansible scripts to set up the elk stack with zeek logging

# Prepare the server

Set the timezone

```bash
sudo dpkg-reconfigure tzdata
```

Set a static IP

```bash
sudo nano /etc/netplan/01-netcfg.yaml 
```

Example network config

```bash
network:
  version: 2
  renderer: networkd
  ethernets:
    eth0:
      dhcp4: no
      addresses: [192.168.8.180/24]
      gateway4: 192.168.8.1
      nameservers:
        addresses: [8.8.8.8,8.8.4.4]
```

Apply the network config

```bash
sudo netplan apply
```

# On the client

```bash
git clone https://github.com/iamckn/elk_ansible
cd elk_ansible
```

Edit the hosts file in that folder and fill in the IP field with the ELK server IP

# Install Elasticsearch

```bash
ansible-playbook setup.yml -u root -k -i hosts -t install_elasticsearch
```

# Install Logstash

```bash
ansible-playbook setup.yml -u root -k -i hosts -t install_logstash
```
# Install Kibana

```bash
ansible-playbook setup.yml -u root -k -i hosts -t install_kibana
```

# Install Filebeat

```bash
ansible-playbook setup.yml -u root -k -i hosts -t install_filebeat
```

# Install Everything

```bash
ansible-playbook setup.yml -u root -k -i hosts
```
