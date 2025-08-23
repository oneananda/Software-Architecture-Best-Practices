# Sessions – Best Practices

Sessions trace down the logged-in user with any means of authentication.  
Handling sessions poorly can make the application vulnerable to serious security issues, as well as lead to degraded performance.  

To ensure both security and efficiency, the following best practices should be followed:

---

## 1. Secure Session Management
- Always use **secure, randomly generated session IDs** that cannot be guessed or predicted.  
- Regenerate session IDs after login, privilege changes, or sensitive operations (to prevent fixation attacks).  
- Store session identifiers only in secure cookies with `HttpOnly`, `Secure`, and `SameSite` attributes.  

---

## 2. Session Lifetime
- Keep session lifetimes **short** and use inactivity timeouts (auto-expire idle sessions).  
- Implement **absolute timeouts** (force logout after a maximum period, even if active).  
- Use sliding expiration cautiously to balance convenience vs. risk.  

---

