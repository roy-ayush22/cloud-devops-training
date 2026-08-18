# Azure Load Balancer

This task focused on creating and configuring an **Azure Load Balancer** to distribute incoming traffic between two IIS web servers.

## Summary of Work Done

* Created an Azure Load Balancer
* Configured a frontend public IP
* Added two VMs to a backend pool
* Configured a health probe
* Created a load-balancing rule
* Used TCP port `80` for web traffic
* Tested the application through the Load Balancer's public IP

## Load Balancer Configuration

```text
Name: load-balancer-instance
Resource Group: load-balance-group
Location: Central India
SKU: Standard
Tier: Regional
```

### Frontend IP

```text
4.224.128.138
```

### Backend Pool

```text
backend-pool-new
├── VM-1 → 10.0.0.5
└── VM-2 → 10.2.0.5
```

![Load Balancer](../03-load-balancer/load-balance.jpeg)

## Health Probe

A TCP health probe was configured to check the availability of the backend servers.

```text
Protocol: TCP
Port: 80
```

![Health Probe Configuration](../03-load-balancer/load-balance-config.jpeg)

## Load Balancing Rule

```text
Protocol: TCP
Frontend Port: 80
Backend Port: 80
```

![Load Balancing Rule](../03-load-balancer/load-balance2.jpeg)

## Testing

The Load Balancer was accessed through its public frontend IP:

```text
4.224.128.138
```

The backend servers returned different responses:

```text
VM-1 → hello from vm 1
VM-2 → hello from vm 2
```

This made it possible to identify which backend VM handled the request.

## Traffic Flow

```text
Client
   │
   │ HTTP : 80
   ▼
Azure Load Balancer
   │
   ├──► VM-1 ──► IIS ──► "hello from vm 1"
   │
   └──► VM-2 ──► IIS ──► "hello from vm 2"
```

## Outcome

Gained hands-on experience with Azure Load Balancer, frontend IPs, backend pools, health probes, load-balancing rules, and distributing web traffic across multiple virtual machines.