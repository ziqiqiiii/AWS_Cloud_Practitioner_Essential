# Networking
****
- [ ] The basic concepts of Networking
- [ ] The difference betweeb public and private networking recources
- [ ] Explain a virtual private gateway using a real life scenario. 
- [ ] Explain a virtual private network (VPN) using a real life scenario.
- [ ] The benefit of hybrid deployments
- [ ] The layers of security used in an IT strategy
- [ ] The services customers use to interact with AWS Global Network
****

### AWS Virtual Private Cloud (VPC)
A networking service that you can use to establish boundaries around your AWS resources.
Amazon VPC enables users to provision an isolated section of the AWS Cloud.
In this isolated section, users can launch resources in a virtual network that users define. 
Within a virtual private cloud (VPC), users can organize their resources into subnets. (A subnet is a section of a VPC that can contain resources such as Amazon EC2 instances.)

---

### Internet Gateway
To allow public traffic from the internet to access your VPC.

---

### Virtual Private Gateway
Allows protected internet traffic to enter into the private resources in a VPC.

Even though your connection to the coffee shop has extra protection, traffic jams are possible because you’re using the same road as other customers.
A virtual private gateway enables you to establish a virtual private network (VPN) connection between your VPC and a private network, such as an on-premises data center or internal corporate network. 
A virtual private gateway allows traffic into the VPC only if it is coming from an approved network.


---

### AWS Direct Connect
A service that lets you to establish a dedicated private connection between your data center and a VPC.  