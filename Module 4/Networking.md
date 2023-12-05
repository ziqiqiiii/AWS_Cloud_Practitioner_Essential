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

---
### Subnets
A subnet is a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private. 
In a VPC, subnets can communicate with each other.

|Public Subnet | Private Subnet |
|:------------:|:--------------:|
| - contain resources that need to be accessible by the public | - ontain resources that should be accessible only through your private network |
| - such as an online store’s website. | - such as a database that contains customers’ personal information and order histories. |

---

### Network Access Control List (ACLs)
A network ACL is a virtual firewall that controls inbound and outbound traffic at the subnet level.

- Each AWS account includes a default network ACL. When configuring your VPC, you can use your account’s default network ACL or create custom network ACLs. 
- By default, your account’s default network ACL allows all inbound and outbound traffic, but you can modify it by adding your own rules. 
- For custom network ACLs, all inbound and outbound traffic is denied until you add rules to specify which traffic to allow.
- Additionally, all network ACLs have an explicit deny rule. This rule ensures that if a packet doesn’t match any of the other rules on the list, the packet is denied.
- ***Stateless packet filtering***
	- Network ACLs perform stateless packet filtering. They remember nothing and check packets that cross the subnet border each way: inbound and outbound. 

---

### Security Groups
A security group is a virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance.

- By default, a security group denies all inbound traffic and allows all outbound traffic. 
- Users can add custom rules to configure which traffic should be allowed; any other traffic would then be denied
- If users have multiple Amazon EC2 instances within the same VPC, users can associate them with the same security group or use different security groups for each instance.
- ***Statefull packet filtering***
	- hey remember previous decisions made for incoming packets.
	- For example, sending a request out from an Amazon EC2 instance to the internet. When a packet response for that request returns to the instance, the security group remembers your previous request. The security group allows the response to proceed, regardless of inbound security group rules.