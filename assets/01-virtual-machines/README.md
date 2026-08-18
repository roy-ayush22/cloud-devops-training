# Azure Virtual Machines

This task covered creating and configuring Windows Server virtual machines in Azure and setting up IIS as a web server on both VMs.

## Summary of Work Done

* Created two Azure Virtual Machines
* Used **Windows Server 2025 Datacenter**
* Configured VM compute resources
* Identified private IP addresses and VNet/subnet configuration
* Installed and configured **IIS (Internet Information Services)**
* Created different test pages on both VMs to identify the server responding to requests

## VM Configuration

### VM-1

* Private IP: `10.0.0.5`
* VNet: `vnet-balancer`
* Subnet: `default`

### VM-2

* Private IP: `10.2.0.5`
* VNet: `vm-2-new-vnet`
* Subnet: `default`

Both VMs use:

```text
OS: Windows Server 2025 Datacenter
Size: Standard D2ls v5
vCPUs: 2
RAM: 4 GiB
```

## IIS Configuration

IIS was installed on both VMs and configured with different responses for testing.

### VM-1

```text
hello from vm 1
```

![IIS on VM-1](../01-virtual-machines/iis-server-on-vm1.jpeg)

### VM-2

```text
hello from vm 2
```

![IIS on VM-2](../01-virtual-machines/iis-server0on-vm2.jpeg)

## Outcome

Gained hands-on experience with Azure Virtual Machines, Windows Server, private IP addressing, VNet/subnet configuration, and hosting a basic web application using IIS.