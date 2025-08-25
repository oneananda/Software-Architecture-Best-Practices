# RPC (Remote Procedure Call)

## 📖 Overview
Remote Procedure Call (**RPC**) is a protocol style that allows a program to execute procedures (functions or methods) on a remote server as if they were local calls.  
Unlike REST or GraphQL (which focus on resources and queries), RPC is **action-oriented**, where the client invokes remote methods directly with parameters.

Two common formats:
- **JSON-RPC**: Lightweight RPC protocol using JSON for requests/responses.
- **XML-RPC**: Older protocol using XML over HTTP to encode calls and results.

---

## ✨ Key Features
- **Procedure-based** – APIs expose *methods* instead of resources.
- **Lightweight** – Minimal overhead compared to SOAP.
- **Transport-agnostic** – Commonly over HTTP, but can use TCP, WebSocket, etc.
- **Synchronous & Asynchronous support** – Depending on implementation.
- **Language-neutral** – Any language that can parse JSON/XML can use it.

---

## 🔑 JSON-RPC

### Request Example
```json
{
  "jsonrpc": "2.0",
  "method": "add",
  "params": [5, 3],
  "id": 1
}
````

### Response Example
````
{
  "jsonrpc": "2.0",
  "result": 8,
  "id": 1
}
````

---

