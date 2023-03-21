# Postgres On Your VM
**Development by:** 
- Findryankp

## Tutorial
1. docker login SERVER_HERE
2. docker pull postgres
3. docker run --rm --name [docker-name] -e POSTGRES_PASSWORD=[password] -e POSTGRES_USER=[username] -p [ip]:5432:5432 -d postgres

* EXAMPLE : 
docker run --rm --name docker-postgres -e POSTGRES_PASSWORD=postgres -e POSTGRES_USER=postgres -p 127.0.0.1:5432:5432 -d postgres