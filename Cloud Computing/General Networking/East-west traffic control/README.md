# East-west traffic control

This refers to a process of the network happening inside a data center, inside the same cloud environment, generally this is to call the internal communication

### Use cases

- Communication between VNet - (VNet Peering)
- Communication within a VNet
- Communication between subnets
- Communication within a subnet

### Implementation 

- **Use Azure Firewall:** We can configfure even for internall based on network and application based rules
- **Use Network Security Groups (NSG):** Azure NSGs can also be used to filter east-west traffic by controlling which resources can communicate with each other within the virtual network.

## Scenarios

- Limiting the spread of internal threats.
- Ensuring compliance with security policies.
- Improving the overall security 


