# CST8912 Lab 2

**Student Name**: Collin MacLeod
**Student ID**: macl0379
**Course**: CST8912 Cloud Solutions Architecture
**Semester**: Fall 2026

## Intorduction

This lab is to practice setting up Peering between virtual machines in seperate and in the same regions. Virtual networks were set up in two regions; 1 in region A: US North Central, 2 in region B: Sweden Central. In each region a virtual machine was set up and peering connections were created between each VM. These connections were tested through Remote Desktop Protocol using Test--Connection and documenting the results.

## Resources

VM | Private IP | VNet (Address Spaces) | 

VM | Expected subnet | Private IP address
vm0 | 10.0.0.0/24 | 10.0.1.4
vm1 | 10.1.0.0/24 | 10.1.0.4
vm2 | 10.2.0.0/24 | 10.2.1.4

## Local Peering vs Global Peering & the Importance of Address Space

Peering is private communication between virtual networks that doesn't need the public internet. The difference betwen Local Peering and Global Peering is available resources to communicate with and associated speeds. Local Peering is communication between two virtual networks in the same region. This allows for secure, low-latency communication between the given regions virtual network. Global Peering is a private communication between virtual networks in different regions with the additional layers making the communication relativley slower than Local Peering.

Each virtual network has an address space that is used for Local and Global Peering. These Address Spaces are what is used to direct traffic to the appropriate network and associated machine. If these address overlap traffic then any communication would be ambiguous.

## Testing Connections

During my lab, all machines were able to connect through peering so no trouble shooting was required. I was also able to confirm that the public internet was not used based on: ``` NetworkIsolationContext: Internet InterfaceAlias: Ethernet ```, and that correct addresses were used. This test does not give any other information beyond showing the network path is open.

## Screenshots

### Virtual Network Listings
 
 !["Virtual Network Listings"](/Screenshots/VN-List.png)

### Peering Listings
 
 Virtual Network 0
 !["Peering Listings VNet 0"](/Screenshots/VNet-0-Peerings.png)
 
 Virtual Network 1
 !["Peering Listings VNet 1"](/Screenshots/VNet-1-Peerings.png)
 
 Virtual Network 2
 !["Peering Listings VNet 2"](/Screenshots/VNet-2-Peerings.png)

 ### Virtual Machines

 Virtual Machine 0
 !["VM 0 overview"](/Screenshots/VM-0.png)

 Virtual Machine 1
 !["VM 1 overview"](/Screenshots/VM-0.png)

 Virtual Machine 2
 !["VM 2 overview"](/Screenshots/VM-0.png)

 ### TCP Connection Results

 Virtual Machine 0 to Virtual Machine 1
!["Connection test VM0 to VM1"](/Screnshots/Connection-Test-VM0-VM1.png)
 
 Virtual Machine 0 to Virtual Machine 2
!["Connection test VM0 to VM1"](/Screnshots/Connection-Test-VM0-VM2.png)
 
 Virtual Machine 1 to Virtual Machine 2
!["Connection test VM0 to VM1"](/Screnshots/Connection-Test-VM1-VM2.png)

### Cleanup Confirmation

!["Cleanup Confirmation"](/Screenshots/Cleanup-Confirmation.png)


