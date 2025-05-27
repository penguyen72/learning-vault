### Option 1: Docker Compose
You can spin up a local postgres server by making the following `docker-compose.yml`
```yml
services:
	database:
		image: postgres
		container_name: local-postgres
		hostname: localhost
		ports:
		- "5432:5432"
		environment:
			POSTGRES_USER: myuser
			POSTGRES_PASSWORD: mypassword
			POSTGRES_DB: mydb
		volumes:
		- authentication_pgdata:/var/lib/postgresql/data
volumes:
	authentication_pgdata:
```

### Option 2: Docker
You can also spin up a local postgres server by running the following Docker command
```bash
docker run --name local-postgres \
  -e POSTGRES_USER=myuser \
  -e POSTGRES_PASSWORD=mypassword \
  -e POSTGRES_DB=mydb \
  -p 5432:5432 \
  -d postgres
```
