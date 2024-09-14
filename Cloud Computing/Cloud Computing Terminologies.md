# Cloud Computing Terminologies

**SSL Termination**

This is a process of decrypting the SSL (Secure Sockets Layer) or TLS (Transport Layer Security) data before sending the data to application layer,

This is typically done to offload the decryption process from the backend servers, which is improving performance.

**Sticky sessions**

A user’s requests are always routed to the same server during their session.

This will be useful when the application stores session data on the server, such as in-memory caches, and it’s crucial that the user consistently interacts with the same server to maintain their session state.

**Server Name Indication (SNI)** 

This is an extension of the TLS (Transport Layer Security) protocol that allows a client to specify the hostname it wants to connect to at the beginning of the handshake process.

For example, imagine you’re trying to visit both example1.com and example2.com, which are hosted on the same server. Your browser uses SNI to tell the server whether it’s connecting to example1.com or example2.com, allowing the server to present the correct certificate for that specific site, ensuring a secure and trusted connection for each visit.
