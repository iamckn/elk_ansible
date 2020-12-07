# elk_ansible
Ansible scripts to set up the elk stack with zeek logging

On the client

```bash
git clone https://github.com/iamckn/wireguard_ansible
cd wireguard_ansible
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
