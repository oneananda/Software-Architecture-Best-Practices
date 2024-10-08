# cURL

cURL (Client URL) is a command-line tool and library for transferring data with URLs. It supports a variety of protocols, including HTTP, HTTPS, FTP, SFTP, and more. cURL is widely used for interacting with web services, downloading files, and testing APIs due to its simplicity and versatility.

## Key Features

- **Protocol Support**: cURL supports a wide range of protocols, including HTTP, HTTPS, FTP, SFTP, SCP, LDAP, MQTT, POP3, and more.
- **Data Transfer**: It allows data transfer to and from servers, making it ideal for downloading or uploading files.
- **Customization**: cURL offers numerous options to customize requests, including setting headers, cookies, and authentication methods.
- **Automation**: It can be used in scripts and automation tasks, making it a powerful tool for developers and system administrators.

### Basic Usage

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

### Intermediate Examples

- Basic POST Request:

```
curl -X POST http://example.com/api/resource -d "param1=value1&param2=value2"
```

The -X option specifies the HTTP method, and -d sends form data.

- POST Request with JSON Data:

```
curl -X POST http://example.com/api/resource \
-H "Content-Type: application/json" \
-d '{"key1":"value1", "key2":"value2"}'
```

- Sending Headers:

```
curl -H "Authorization: Bearer token123" http://example.com/api/resource
```

This adds an Authorization header to the request.

- Handling Redirects:

```
curl -L http://example.com/redirect
```

The -L flag follows redirects.

### Advanced Examples

- Using cURL with Cookies:

```
curl -c cookies.txt -b cookies.txt http://example.com
```

The -c option saves cookies to a file, and -b sends them with the request.

- Upload a File

```
curl -X POST http://example.com/upload \
-F "file=@/path/to/file.txt"
```

The -F flag is used to upload files with multipart/form-data.

- Sending Multiple Headers

```
curl -X GET http://example.com \
-H "Authorization: Bearer token123" \
-H "Accept: application/json"
```

Add multiple headers by repeating the -H flag.

- Handling Timeouts

```
curl -m 10 http://example.com
```

The -m option sets a maximum time in seconds for the request.


- Verbose Output for Debugging

```
curl -v http://example.com
```

The -v option makes cURL provide detailed information about the request and response, which is useful for debugging.

- Sending Data with Custom Methods

```
curl -X PUT http://example.com/api/resource/1 \
-H "Content-Type: application/json" \
-d '{"name": "Updated Name"}'
```

`PUT` method to update a resource.

- Setting User Agent

```
curl -A "Mozilla/5.0" http://example.com
```

- Rate Limiting

```
curl --limit-rate 100K http://example.com
```

Limits the request's download speed to 100KB/s.

- Authentication 

```
curl -u username:password http://example.com
```

Please note : This is very basic level authentication, if the username or password contains special characters then we need to escape them and use it.

- Complex Requests with JSON and Headers

```
curl -X POST http://example.com/api/resource \
-H "Content-Type: application/json" \
-H "Authorization: Bearer token123" \
-d '{
  "name": "New Resource",
  "settings": {
    "enabled": true,
    "threshold": 15
  }
}'
```

Sending complex requests with multiple headers in the POST request.