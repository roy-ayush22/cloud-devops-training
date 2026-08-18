# Azure VNet Peering

This task focused on establishing private network connectivity between two Azure Virtual Networks using **VNet Peering**.

## Summary of Work Done

* Worked with two Azure Virtual Networks
* Configured VNet-to-VNet peering
* Connected the VNets containing VM-1 and VM-2
* Used private IP addresses for communication
* Tested connectivity using `ping`
* Verified communication between both VMs

## Network Configuration

```text
vnet-balancer
      │
      │ VNet Peering
      │
      ▼
vm-2-new-vnet
```

The two VMs had the following private IP addresses:

```text
VM-1 → 10.0.0.5
VM-2 → 10.2.0.5
```

![VNet Peering Configuration](../02-vnet-peering/v-net-peering-config.jpeg)

![VNet Peer 1](../02-vnet-peering/vnet-peer-1.jpeg)

![VNet Peer 2](../02-vnet-peering/vnet-peer-2.jpeg)

## Connectivity Testing

### VM-1 → VM-2

```text
Target: 10.2.0.5
Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
```

![Ping VM-2](../02-vnet-peering/ping-1.jpeg)

### VM-2 → VM-1

```text
Target: 10.0.0.5
Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
```

![Ping VM-1](../02-vnet-peering/ping-2.jpeg)

## Outcome

Successfully established private connectivity between the two VNets and verified that the VMs could communicate with each other using their private IP addresses.