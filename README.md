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

## Enhancements
Add a bind mount to the `samp_db` service for a file called `init.sql`, that populates the database with data on initialisation.
```
volumes:
    - ./init.sql:/docker-entrypoint-initdb.d/init.sql
```

Add a bind mount to the `samp_db` service for a directory called `sql`, so that the database storage files are stored in this directory instead of letting docker generate a directory to store the data.
```
volumes:
    - ./sql:/var/lib/mysql
```

Expose port `3306` for the `samp_db` service to allow connections form outside the container, so that external applications (e.g. a web server) can access the database.
```
ports:
    - "3306:3306"
```