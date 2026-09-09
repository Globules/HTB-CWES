# HyperText Transfer Protocol (HTTP) — Practice

To get the flag, start the exercise, then use cURL to download the file returned by '/download.php' in the server shown above.

---

## Solve

```bash
┌──(kali㉿kali)-[~]
└─$ curl -ski http://154.57.164.82:32560/download.php | grep "flag"
Content-Disposition: attachment; filename="flag.txt"
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ curl -ski 'http://154.57.164.82:32560/download.php?filename=flag.txt'
HTTP/1.1 200 OK
Date: Wed, 09 Sep 2026 12:01:29 GMT
Server: Apache/2.4.41 (Ubuntu)
Content-Description: File Transfer
Cache-Control: no-cache, must-revalidate
Expires: 0
Content-Disposition: attachment; filename="flag.txt"
Content-Length: 20
Pragma: public
Content-Type: text

HTB{64$!c_cURL_u$3r}  
```

---

## Notes

curl : 

- `-s (--silent)` : Silent mode. It hides the progress meter and error messages
- `-k (--insecure)` : Allow insecure SSL/TLS connections without verifying the server's security certificate
- `-i (--include)` :  Includes the HTTP response headers in the output (useful for debugging).

