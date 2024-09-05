# cURL

cURL (Client URL) is a command-line tool and library for transferring data with URLs. It supports a variety of protocols, including HTTP, HTTPS, FTP, SFTP, and more. cURL is widely used for interacting with web services, downloading files, and testing APIs due to its simplicity and versatility.

## Key Features

- **Protocol Support**: cURL supports a wide range of protocols, including HTTP, HTTPS, FTP, SFTP, SCP, LDAP, MQTT, POP3, and more.
- **Data Transfer**: It allows data transfer to and from servers, making it ideal for downloading or uploading files.
- **Customization**: cURL offers numerous options to customize requests, including setting headers, cookies, and authentication methods.
- **Automation**: It can be used in scripts and automation tasks, making it a powerful tool for developers and system administrators.

## Basic Usage

- To fetch the content of a URL:

```
curl https://example.com
```

- GET Request with Query Parameters:

```
curl "http://example.com/search?query=example"
```

- Download a File:

```
curl -O http://example.com/file.zip
```

Note: The -O flag saves the file with its original name.

- Save Output to a File:

```
curl http://example.com -o output.html
```

