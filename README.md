# ansible-vmware

Ansible playbooks to manage vmware infrastructure.

Most of this playbooks use *name* as the parameter to identify a VM. However, name are not necessarily unique in a VMWare cluster. If this is the case, playbook should be modified to use *uuid*, which is a unique identifier to a VM.

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

### get_vm_info.yml

Get VMWare Machine Guest info.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password

### get_vm_size.yml

Get VM size, according to real storage use.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name

### get_vm_snapshots.yml

Get snapshots of a VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name

### take_snapshot.yml

Take snapshot from VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name
- snapshot_name: Snapshot name

### remove_snapshot.yml

Remove snapshot from VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name
- snapshot_name: Name of existent snapshot

### revert_to_snapshot.yml

Revert VM to snapshot.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name
- snapshot_name: Name of existent snapshot

### poweron_vm.yml

Power on a VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name

### poweroff_vm.yml

Power off a VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name

### raise_vm_cpu.yml

Raise cpu number for a VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name
- cpu_number: Number of CPUs

### raise_vm_memory.yml

Raise cpu number for a VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name
- memory_size: Size of memory

### set_vm_os_version.yml

Configure os version to VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name
- os_version: OS Version

### set_hot_add_values.yml

Set "hot add" values to VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name

### unset_hot_add_values.yml

Unset "hot add" values to VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name

### add_disk.yml

Add disk to a VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name

### delete_last_disk.yml

Delete last disk from VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name

### resize_disk.yml

Resizing disk in VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM Name
- scsi_controller: SCSI controller
- unit_number: Unit number

### rename_vm.yml

Rename VM.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM name
- new_vm_name: New vm name

### move_vm.yml

Move VM to a new folder.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM name
- destination_folder: Destination folder

### update_vmware_tools.yml

Upgrade vmware tools on VM. This playbook should be used if installed VMWare tools are the one provided by VMWare. If you are using VMWare tools provided by the OS, using native OS packages are recommended.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM name

### clone_vm_from_template.yml

Clone a new VM from a template. Another VM can be used as source.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- datastore: VMWare datastore
- vm_name: VM name
- template_name: Template name
- folder_name: Folder name
- cluster_name: Cluster name

### clone_template_from_template.yml

Clone a new template from an existent template.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- datastore: VMWare datastore
- vm_name: VM name
- template_name: Template name
- folder_name: Folder name
- cluster_name: Cluster name

### remove_vm.yml

Remove a VM. Is probably a better idea to remove VMs according to *uuid* instead of names, due to the fact that VM names are not necessarily unique.

Required input variables:

- vcenter_ip: vCenter IP or hostname
- vcenter_username: vCenter username
- vcenter_password: vCenter password
- datacenter: VMWare datacenter
- vm_name: VM name
