recreated for https://jordancrawford.kiwi/setting-up-tinc/

Create a `/hosts` file with the nodes that you want to include in the VPN:

```
[vpn]
node1 ansible_host=<local server ip> vpn_ip=10.0.0.2 tinc_name=home
node2 ansible_host=<vpn ip> vpn_ip=10.0.0.1 tinc_name=cloud
[removevpn]
```

Run the playbook:

```bash
ansible-playbook site.yml -i hosts
```

make sure tincd is running on both nodes `tincd` 