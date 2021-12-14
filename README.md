# ansible-vmware

Ansible playbooks to manage vmware infrastructure.

## List of playbooks

You can run the playbook as follows:

```console
ansible-playbook -i 'localhost,' playbook.yml
```

Extra vars are prompted. You can run the playbook in a single command line passing the extra vars like this:

```console
ansible-playbook -i 'localhost,' -e "extra_var1=extra_var_value1 extra_var2=extra_var_value2 ..." playbook.yml
```

### get_vm_settings.yml

Get summary information about a VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name

### get_vm_list.yml

Get a list of VMs from a Cluster.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password

### get_vm_disks.yml

Get disk information for a virtual machine.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name
