In `inventory/inventory.ini`, `installer-uefi` and `installer-bios` are defined.

So for testing installation of a distribution, create a soft-link from distribution host_vars to installer-uefi.yml or installer-bios.yml depending of the machine type.

For testing bios and uefi I used the following workflow:

*With hostname `installer-uefi` defined in `/etc/hosts`*
```sh
cd inventory/host_vars/
unlink installer-uefi.yml
ln -s rocky10-uefi.yml installer-uefi.yml

cd ../..
ansible-playbook -l installer-uefi playbook.yml
```

