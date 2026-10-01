# AI-for-IT-Automation-and-Security
In this project, I will redesign a company's network to securely connect two acquired smaller companies . I will use AI-supported tools to create architecture diagrams, model the network in GNS3, and explore threat detection and IT automation. I will evaluate how these solutions improve security, scalability, performance, and cost efficiency.


Phase 1: First, I cloned the repository to my local VScode. Next, I had Lucidcharts fraft a new networking schema combining the larger compnay with the two smaller acquired companies. Following this step, I then re-created this step in my GNS3 software. 

<img width="775" height="722" alt="Screenshot 2026-09-30 at 6 42 06 PM" src="https://github.com/user-attachments/assets/dbdc2230-b4d9-4000-a33e-f7d94c7d7018" />


The diagram depicts a segmented enterprise network with two clinic star topologies and a secure central core/DMZ.

- Internet/WAN links: External Internet endpoints provide connectivity into the company and clinic networks. Dashed uplinks indicate WAN or inter-site connectivity, enabling the clinics to reach shared enterprise services.
- Routers A and B: Each clinic has a local router at the center of its star topology. The routers aggregate local traffic, provide the clinic’s upstream/WAN path, and connect local switches and wireless access points to the enterprise edge.
- Edge router/firewall: The enterprise perimeter device separates outside, internal, and DMZ traffic. Its labeled outside, inside, and DMZ interfaces show why it is included: it enforces perimeter policy, controls north–south traffic, and provides the DMZ gateway.
- Core switch: The core switch is the internal backbone and performs inter-VLAN routing. It connects the perimeter firewall to internal server and user/IoT segments while allowing policy-controlled communication between them.
- Access switches: Clinic A uses Switch A1 and Switch A2; Clinic B uses Switch B1 and Switch B2; the enterprise core also includes Switch 1. These switches provide local Layer 2 connectivity for PCs, servers, wireless access points, and shared services.
- VLAN 10 Staff (192.168.10.0/24): This segment contains Clinic A staff PCs. It separates employee endpoints from server and IoT traffic, improving security and traffic management.
- VLAN 30 IoT (192.168.30.0/24): This segment is reserved for IoT devices and is connected to wireless access infrastructure. Its separation limits the impact of a compromised or poorly secured IoT device.
- VLAN 20 Server (192.168.20.0/24): This server network contains shared enterprise services. Keeping servers in a dedicated VLAN supports centralized access control and reduces exposure to endpoint networks.
- Clinic A and Clinic B PCs: Each clinic includes multiple client PCs with addresses in its local subnet. They represent staff workstations and demonstrate endpoint connectivity through the clinic switches and routers.
- Wireless access points: WAP A and WAP B provide wireless access for clinic users or devices. Their placement at the edge of each clinic topology reflects local wireless connectivity while preserving the clinic’s routing and segmentation boundaries.
Enterprise servers: The Ubuntu EHR Server supports clinical-record access; the Ubuntu File Server provides shared file services; and the Ubuntu Backup Server supports data protection and recovery. Their dedicated server addresses and VLAN placement indicate centralized, protected services.
- Clinic A and Clinic B servers: Each clinic has a local server, representing site-specific applications or services that need to remain close to users while still connecting through the clinic network.
- Azure Cloud Shell: This virtual-server component represents a cloud-hosted management or administration environment. It provides a remote/cloud execution point rather than a conventional on-premises server.
- DMZ: The isolated DMZ is a separate network zone with its own gateway. It is included to host externally reachable services while preventing direct access to internal networks; the diagram explicitly notes that DMZ isolation and inter-VLAN access are controlled by policy.
- Legend and notation: Solid lines identify internal links, dashed lines identify WAN/uplink paths, VLAN symbols mark segmentation boundaries, and the DMZ symbol identifies the isolated security zone.
- 
No dedicated AI processing unit or AI service is explicitly shown. The Azure Cloud Shell could be used to administer or run cloud workloads, but the diagram does not identify it as an AI component.
