# Bastion Host (or Bastion Server)

A **bastion** is often referred to as a **jump server**. Both terms describe a similar type of server that acts as an intermediary for accessing resources in a private network. 

### **Bastion Host (or Bastion Server)**:
- A **bastion host** is a secure server that typically sits in a **public subnet** and is used to provide access to resources in a **private subnet**.
- It is designed with a focus on **security**, often hardened and monitored closely, since it serves as the only point of entry into the private network from the public internet.

### Why Use a Bastion/Jump Server:
- **Controlled Access**: Only the bastion/jump server is exposed to the internet, minimizing the attack surface of the private network.
- **Security**: By restricting direct access to the internal systems, the bastion or jump server provides an additional security layer.
- **Auditing**: Activity on the bastion/jump server can be logged and monitored, making it easier to track access to internal resources.

### Typical Use Case in Cloud:
- In AWS, for example, a **bastion host** might be placed in a **public subnet** to allow **SSH** or **RDP** access to resources in a **private subnet** that do not have direct internet access.
- Similarly, a **jump server** in Azure or Google Cloud serves the same purpose, acting as a controlled access point into the internal cloud infrastructure.

In conclusion, while the terms are used interchangeably, **bastion** often emphasizes security, while **jump server** tends to emphasize the practical function of "jumping" between networks.

