# HTTP Requests and Responses — Practice

Q1 : What is the HTTP method used while intercepting the request? -> GET

Q2 : Send a GET request to the  server, and read the response headers to find the version of Apache running on the server, then submit it as the answer. (answer format: X.Y.ZZ)

---

## Solve 

```bash
curl -ski 'http://154.57.164.76:32353' 

HTTP/1.1 200 OK
Date: Wed, 09 Sep 2026 12:34:56 GMT
Server: Apache/2.4.41 (Ubuntu)
```

---

## Notes

curl : 

- `-s (--silent)` : Silent mode. It hides the progress meter and error messages
- `-k (--insecure)` : Allow insecure SSL/TLS connections without verifying the server's security certificate
- `-i (--include)` :  Includes the HTTP response headers in the output (useful for debugging).




