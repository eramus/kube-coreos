# Initialize network

```
virsh --connect qemu:///system net-start default
```

# Initialize images

```
cd dir
qemu-img create -f qcow2 -b /path/to/coreos_production_qemu_image.img /path/to/vm.qcow2
virt-install --connect qemu:///system --import --name vm --ram 256 --vcpus 1 --os-type=linux --os-variant=virtio26 --disk path=/path/to/etcd3.qcow2,format=qcow2,bus=virtio --filesystem /path/to/user_data/,config-2,type=mount,mode=squash -w network=default,mac=52:54:00:fe:b0:03 --vnc --noautoconsole
```


