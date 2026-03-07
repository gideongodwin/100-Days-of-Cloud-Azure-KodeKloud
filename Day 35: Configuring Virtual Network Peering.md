## Day 35: Configuring Virtual Network Peering

#### Task Details:
The Nautilus DevOps team has been tasked with demonstrating the use of VNet Peering to enable communication between two VNets. One VNet will be a private VNet that contains a private Azure VM, while the other will be a public VNet containing a publicly accessible Azure VM.

1) Existing Azure Resources:

Public VM: nautilus-pub-vm is already in the public VNet.
Private VNet and VM: nautilus-priv-vnet and nautilus-priv-vm exist in the private VNet with its subnet: nautilus-priv-subnet.
2) Create VNet Peering:

Create a VNet Peering between the Public VNet and Private VNet.
VNet Peering Name: nautilus-pub-to-priv-peering.
3) Test the Connection:

SSH into the public VM and verify that you can ping the private VM.
