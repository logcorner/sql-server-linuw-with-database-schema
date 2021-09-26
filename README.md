# sql-server-linux-with-database-schema

# Build docker file

docker build -t database-image . --build-arg SA_PASSWORD='PassW0rd'

# run database-container on port 1433
docker run -d -p 1433:1433 --name database-container database-image

# attach bas shell to the container database-container
Docker exec -it database-container "bash"
/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'PassW0rd'

# run sql queries
select name from sys.databases


# docker compose
docker-compose build
docker-compose up

docker volume inspect 
sql-server-linux-with-database-schema_mssql-server-linux-data
{
    "CreatedAt": "2021-09-26T10:35:04Z",
    "Driver": "local",
    "Labels": {
        "com.docker.compose.project": "sql-server-linux-with-database-schema",
        "com.docker.compose.version": "1.29.2",
        "com.docker.compose.volume": "mssql-server-linux-data"
    },
    "Mountpoint": "/var/lib/docker/volumes/sql-server-linux-with-database-schema_mssql-server-linux-data/_data",
    "Name": "sql-server-linux-with-database-schema_mssql-server-linux-data",
    "Options": null,
    "Scope": "local",
    "CreatedTime": 1632652504000,
    "Containers": {
        "e6f80acd471269b8ae2e5c4c7df164fcb4894d25bb24ccd89d63172c3b8aec78": {
            "Name": "sql-server-linux-with-database-schema_logcorner.workshop.service.data_1",
            "Destination": "/var/opt/mssql/data"
        }
    }
}

Docker exec -it sql-server-linux-with-database-schema_logcorner.workshop.service.data_1 "bash"
/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'MyC0m9l&xP@ssw0rd'


select name from sys.databases
go
use Northwind

go
SELECT *   FROM [Northwind].[dbo].[Orders]

go


https://docs.microsoft.com/en-us/sql/linux/tutorial-sql-server-containers-kubernetes?view=sql-server-ver15

