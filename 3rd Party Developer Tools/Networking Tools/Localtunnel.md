# Localtunnel

Localtunnel allows you to easily share a local web service on your development machine without needing to deploy it to a public server. It provides a secure tunnel to your localhost, making it accessible from anywhere over the internet.

## Features

- **Easy to Use**: Start a tunnel with a single command.
- **Custom Subdomains**: Request a specific subdomain on the Localtunnel server.
- **Secure**: Provides an HTTPS URL for secure access.

## Installation

To install Localtunnel, you need Node.js (version 10 or later) installed on your machine.

Install Localtunnel globally using npm:

```
npm install -g localtunnel
```

## Basic Usage

To start a tunnel and expose your local server to the internet, use the following command:

```
lt --port 8000
```