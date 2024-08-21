# UNDER DEVELOPMENT, DO NOT USE

# Ludus_Foreign_domain

Ansible role to create a stand alone domain and domain controller. 

## Example 

```yaml
ludus: 
  - vm_name: "{{ range_id }}-Internal-VLAN30-devdc01"
    hostname: "devdc01"
    template: win2016-server-x64-template
    vlan: 30
    ip_last_octet: 10
    ram_gb: 4
    cpus: 1
    windows:
      sysprep: true 
    roles:
      - ludus_foreign_domain
    role_vars:
      new_domain_name: "dev.test.local"
      new_domain_netbios_name: "dev"