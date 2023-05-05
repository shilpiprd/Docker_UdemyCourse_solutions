Task for Session3, Assignment1: 
_____

- Run a nginx, a mysql, and a httpd(apache ) server
- Run all of them `—detach` (or -d), name them with `—name`
- Assign each container different ports coz each container can’t run in the same port as other containers. So nginx is going to be our proxy in this case.
- nginx should listen on `80:80`, httpd on `8080:80`, mysql on `3306:3306.`
    - When running mysql, use the env option (or -e) to pass in `MYSQL_RANDOM_ROOT_PASSWORD=yes`
- Use `docker container logs` on `mysql` to find the random password it created on startup.
- Clean it all up with `docker container stop` and `docker container rm`( both can accept multiple names or ID’s ).
- Use `docker container ls` to ensure everything is correct before and after cleanup.

Some additional information to keep: 
______ 
docker ps is same as docker container ls

on doing curl localhost, you’ll see about nginx 

on doing `curl [localhost](http://localhost):8080`  youll see about apache,
