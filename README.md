# Collecting IP Address from Huawei AR1220 Router Interfaces with Ansible ipaddr filter.

- Basic script to collect ip address from Huawei AR1220 Router with IPADDR FILTER to handle and get different kinds of ip address informations like network address, gateway, mask, broadcast, last usage ip address and many others. This script execute some tasks to collect the interfaces data, then with ipaddr filter, manipulate the ip addresses that its important and finally save it in a Jinja .txt file.

## Execution Requirements

- Tested with Ubuntu 18 terminal in a Windows 10 PC (works fine in linux enviroment).
- Tested with Ansible version 2.9
- Tested with Python version 2.7
- netaddr Python package to manipulate the input data

`sudo pip install netaddr`

## Target Requirements

- Huawei Router model AR1200 Series.
- SSH version 2.0 or higher configured.

## Variables

- model.txt.j2 -> Jinja file, edit as you want and do the same thing in playbook yaml file
- hosts -> Edit your ansible hosts/routers_huawei
- /group_vars/all.yml -> Edit your username and password to access the targets via ssh. (Recommended for enviroment with TACACS+ or RADIUS servers)

## How to use

`ansible-playbook huawei-collect-interface-ip.yml`

## What does this script do?

- Collect all interfaces facts from Huawei Router
- The ipaddr filter helps you to handle the collected ip addresses as you want
- Then save the results using a Jinja file

## About ipaddr Filter

- Read the official documentation for more details: [ipaddr filter](https://docs.ansible.com/ansible/2.9/user_guide/playbooks_filters_ipaddr.html)

## Author Information

This role was created by [João Vitor C. Medeiros](https://www.linkedin.com/in/joaovitorcm/)