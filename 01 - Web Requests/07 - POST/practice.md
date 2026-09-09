# POST — Practice

Obtain a session cookie through a valid login, and then use the cookie with cURL to search for the flag through a JSON POST request to '/search.php'
Authenticate to 154.57.164.71 , with user "admin" and password "admin"

## Solve

![alt text](image.png)

Remove the user agent header and send the curl request : 

```bash
curl 'http://154.57.164.71:32604/search.php' \
  -H 'Accept: */*' \
  -H 'Accept-Language: en-US,en;q=0.9' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -b 'PHPSESSID=9t0n1r371lbd1oao2463amv687' \
  -H 'Origin: http://154.57.164.71:32604' \
  -H 'Referer: http://154.57.164.71:32604/' \
  --data-raw '{"search":"flag"}' \
  --insecure
["flag: HTB{p0$t_r3p34t3r}"]      
```