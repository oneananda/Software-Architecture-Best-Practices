# Comparison between SAST and DAST

| **Criteria**                 | **SAST (Static Application Security Testing)**  | **DAST (Dynamic Application Security Testing)**    |
|------------------------------|-------------------------------------------------|---------------------------------------------------|
| **Testing Phase**             | Early in the development lifecycle (before deployment). | Late in the development lifecycle or in production (after deployment). |
| **Access to Code**            | Requires access to source code, bytecode, or binary code. | Does not require access to the source code. |
| **Type of Testing**           | White-box testing (internal view of the application). | Black-box testing (external view, simulating attacks). |
| **Scope**                     | Focuses on finding vulnerabilities in the code itself. | Focuses on identifying vulnerabilities in the running application. |
| **Detectable Vulnerabilities** | Code-based vulnerabilities like buffer overflows, SQL injection, hardcoded secrets. | Runtime vulnerabilities like authentication flaws, insecure configurations, session management issues. |

