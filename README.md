# samp-server-docker-compose
Example docker-compose file for SA-MP servers using a MySQL database.

## Command to start all services at once
```
docker-compose up
```

## Commands to enter running containers
```
docker exec -it samp bash
docker exec -it samp_db mysql -u root -p
```
