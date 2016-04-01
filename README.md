[![StackStorm](https://github.com/stackstorm/st2/raw/master/stackstorm_logo.png)](http://www.stackstorm.com)

# st2-netops-base_config Integration Pack
With this pack you get the possibility to ensure a base_config on Cisco IOS-Switches. This works with the defined aliases and the called ansible-playbook **site.yml** behind the scene. The pack could be extended to support different vendors, os-types and more roles. At the moment the config for ntp and snmp gets ensured. The ansible playbooks and roles are based on the [webinar content][1] of **privateip**.

## Configuration

To get Ansible work with the IOS-modules you have to install it on the StackStorm-server. The **devel**-branch includes all needed modules.
```sh
$ git clone http://github.com/ansible/ansible.git
$ cd ansible
$ git checkout devel
$ git submodule init
$ git submodule update
$ pip uninstall ansible
$ python setup.py install
$ ansible --version
ansible 2.0.1.0 (stable-2.0-network 49f7e6a12c) last updated 2016/03/01 20:57:24 (GMT +200)
  lib/ansible/modules/core: (detached HEAD 72540d1f0c) last updated 2016/03/01 20:57:27 (GMT +200)
  lib/ansible/modules/extras: (detached HEAD 51cddf2b35) last updated 2016/03/01 20:57:28 (GMT +200)
```

## Sensors

/

## Actions

This pack adds:
* action **ensure_base_config**
* alias **netops.ensure_base_config**
* ansible-playbook **site.yml**
* ansible-role **network_facts**
* ansible-role **ntp**
* ansible-role **snmp**
* ansible-role **write_cfg**

## Install
```sh
$ st2 run packs.install packs=st2-netops-base_config repo_url=https://github.com/smnmtzgr/st2-netops-base_config
```
[1]: https://github.com/privateip/Ansible-Webinar-Mar2016
