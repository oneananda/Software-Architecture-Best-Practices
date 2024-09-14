# SYN Flood Attack

A SYN flood is a type of Denial of Service (DoS) attack that targets the handshake process of the TCP/IP protocol used for establishing a connection between a client and a server. 

A SYN flood attack is like someone repeatedly knocking on your door without any intention of entering, just to keep you busy and prevent you from attending to real visitors.

### How SYN Flood Attacks Work

1. **Normal TCP Handshake:**
   - Normally, when two computers want to talk to each other over the internet, they perform a "handshake," like a polite greeting:
     1. **Step 1:** The client sends a “Hello” (SYN packet) to the server.
     2. **Step 2:** The server responds with a “Hello back” (SYN-ACK packet).
     3. **Step 3:** The client replies with an “Okay, let’s talk” (ACK packet), and the connection is established.

2. **SYN Flood:**
   - In a SYN flood, the attacker sends a lot of those initial “Hello” messages (SYN packets) but never replies to the server’s “Hello back” (SYN-ACK).
   - The server keeps waiting for the final “Okay, let’s talk” (ACK) that never comes. It has to keep resources reserved for these half-open connections, which ends up using a lot of its capacity.

3. **Why It’s a Problem:**
   - **Wasted Resources:** (`Resource Exhaustion`) The server gets bogged down with all these unfinished handshakes, using up memory and processing power.
   - **Unavailable Service:** (`Service Unavailability`) Legitimate users who actually want to connect can’t get through because the server is too busy dealing with the fake requests.

### How to Protect Against SYN Floods

1. **SYN Cookies:** Imagine checking the sincerity of every “Hello” before reserving time for a full conversation. This prevents your resources from being held hostage by fake handshakes.

2. **Rate Limiting:** This is like setting a rule that says, “Only a certain number of ‘Hellos’ per minute,” so you don’t get overwhelmed.

3. **Firewalls and IPS:** Think of these as security guards who can spot the fake handshakes and block them at the door.

4. **Timeout Reduction:** If a handshake doesn’t complete quickly, drop it and move on. It’s like hanging up on a prank call faster.

5. **Load Balancing and Redundancy:** Spread out the connections across multiple servers or have backups ready, so no single server gets overloaded.

Understanding SYN floods is crucial for designing robust systems that can withstand malicious attempts to disrupt service availability.