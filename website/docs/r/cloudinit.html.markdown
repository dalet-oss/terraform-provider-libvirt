---
layout: "libvirt"
page_title: "Libvirt: libvirt_cloudinit_disk"
sidebar_current: "docs-libvirt-cloudinit-disk"
description: |-
  Manages a cloud-init ISO disk to attach to a domain
---

# libvirt\_cloudinit\_disk

Manages a [cloud-init](http://cloudinit.readthedocs.io/) ISO disk that can be
used to customize a domain during first boot.

## Example Usage

```hcl
resource "libvirt_cloudinit_disk" "commoninit" {
  name      = "commoninit.iso"
  user_data = data.template_file.user_data.rendered
}

data "template_file" "user_data" {
  template = file("${path.module}/cloud_init.cfg")
}

```

where `cloud_init_cfg` is a file on same dir level of the terraform tf.file
```
#cloud-config
ssh_pwauth: True
chpasswd:
  list: |
     root:linux
  expire: False
```

In this example we change with help of cloud-init the root pwd.
Take also insipiration from ubuntu.tf https://github.com/dmacvicar/terraform-provider-libvirt/blob/master/examples/v0.12/ubuntu/ubuntu-example.tf

## Argument Reference

The following arguments are supported:

* `name` - (Required) A unique name for the resource, required by libvirt.
* `region` - (Optional) The libvirt client region to create the resource to.
* `az` - (Optional) The libvirt client availability-zone to create the resource to.
* `pool` - (Optional) The pool where the resource will be created.
  If not given, the `default` pool will be used.
  For user_data, network_config and meta_data parameters have a look at upstream doc:
   http://cloudinit.readthedocs.io/en/latest/topics/datasources/nocloud.html#datasource-nocloud

* `user_data` - (Optional)  cloud-init user data.
* `meta_data` - (Optional)  cloud-init user data.
* `network_config` - (Optional) cloud-init network-config data.
