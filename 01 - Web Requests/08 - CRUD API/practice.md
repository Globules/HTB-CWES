# CRUD API — Practice

First, try to update any city's name to be 'flag'. Then, delete any city. Once done, search for a city named 'flag' to get the flag.

---

## Solve 

```bash
curl -X PUT http://154.57.164.73:31727/api.php/city/london -d '{"city_name":"flag", "country_name":"flag"}' -H 'Content-Type: application/json'
curl -X DELETE http://154.57.164.73:31727/api.php/city/Leeds
curl http://154.57.164.73:31727/api.php/city/flag

[{"city_name":"flag","country_name":"HTB{crud_4p!_m4n!pul4t0r}"}]      
```

---

## Notes

- `PUT` -> Update a resource
- `DELETE` -> Delete a resource
- `GET` -> Read a resource
- `-X` -> Specify the HTTP method
- `-d` -> Send data in the request body
- `-H` -> Add an HTTP header
- `Content-Type: application/json` -> Body is JSON
- `/city/london` -> Target the `london` resource
- `/city/flag` -> Read the `flag` resource