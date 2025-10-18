# qemu

## image
qemu-img create -f qcow2 image-file size
qemu-img create -f raw image-file size


## run

### x84_64
qemu-system-x86_64 [machine opts] \
                   [cpu opts] \
                   [accelerator opts] \
                   [device opts] \
                   [backend opts] \
                   [interface opts] \
                   [boot opts]
