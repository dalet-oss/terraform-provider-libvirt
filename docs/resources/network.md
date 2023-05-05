---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "libvirt_network Resource - terraform-provider-libvirt"
subcategory: ""
description: |-
  
---

# libvirt_network (Resource)





<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String)

### Optional

- `addresses` (List of String)
- `autostart` (Boolean)
- `az` (String)
- `bridge` (String)
- `dhcp` (Block List, Max: 1) (see [below for nested schema](#nestedblock--dhcp))
- `dns` (Block List, Max: 1) (see [below for nested schema](#nestedblock--dns))
- `dnsmasq_options` (Block List, Max: 1) (see [below for nested schema](#nestedblock--dnsmasq_options))
- `domain` (String)
- `mode` (String)
- `mtu` (Number)
- `region` (String)
- `routes` (Block List) (see [below for nested schema](#nestedblock--routes))
- `xml` (Block List, Max: 1) (see [below for nested schema](#nestedblock--xml))

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--dhcp"></a>
### Nested Schema for `dhcp`

Optional:

- `enabled` (Boolean)


<a id="nestedblock--dns"></a>
### Nested Schema for `dns`

Optional:

- `enabled` (Boolean)
- `forwarders` (Block List) (see [below for nested schema](#nestedblock--dns--forwarders))
- `hosts` (Block Set) (see [below for nested schema](#nestedblock--dns--hosts))
- `local_only` (Boolean)
- `srvs` (Block List) (see [below for nested schema](#nestedblock--dns--srvs))

<a id="nestedblock--dns--forwarders"></a>
### Nested Schema for `dns.forwarders`

Optional:

- `address` (String)
- `domain` (String)


<a id="nestedblock--dns--hosts"></a>
### Nested Schema for `dns.hosts`

Optional:

- `hostname` (String)
- `ip` (String)


<a id="nestedblock--dns--srvs"></a>
### Nested Schema for `dns.srvs`

Optional:

- `domain` (String)
- `port` (String)
- `priority` (String)
- `protocol` (String)
- `service` (String)
- `target` (String)
- `weight` (String)



<a id="nestedblock--dnsmasq_options"></a>
### Nested Schema for `dnsmasq_options`

Optional:

- `options` (Block List) (see [below for nested schema](#nestedblock--dnsmasq_options--options))

<a id="nestedblock--dnsmasq_options--options"></a>
### Nested Schema for `dnsmasq_options.options`

Optional:

- `option_name` (String)
- `option_value` (String)



<a id="nestedblock--routes"></a>
### Nested Schema for `routes`

Required:

- `cidr` (String)
- `gateway` (String)


<a id="nestedblock--xml"></a>
### Nested Schema for `xml`

Optional:

- `xslt` (String)

