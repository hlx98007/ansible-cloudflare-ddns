Cloudflare DDNS via Ansible
==

Use this ansible script to setup DDNS for your dynamic IP box, you can setup in
cronjob.

Installation
---
```
pip3 install -r requirements.txt
```

Usage
---
```
ansible-playbook setup-ddns.yml -e "cf_api_email=cf@email.com" \
                                -e "cf_api_key=cl0udflar3ap1k3y" \
                                -e "record=ddns.domain.tld" \
                                -e "zone=domain.tld"
```

By default it is assumed to be A record. Ansible is using the
[ipif_facts](https://docs.ansible.com/ansible/latest/modules/ipify_facts_module.html) module to obtain your public IP.

Value Overrides
---
The first value is the default value.

```
cf_proxied: yes/no
cf_solo: yes/no
cf_type: A/CNAME/MX/...
cf_state: present/absent
```
