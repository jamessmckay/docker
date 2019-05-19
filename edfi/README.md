# Ed-Fi Docker Compose
Docker compose file that creates a Docker environment for development.

## Images

The compose file creates and runs the following images:
* PostgreSql 10 using the Alpine image.
  * Port: 5340
  * Named: pg10
  * Connection String: `Server=localhost;Database=postgres;Username=postgres;Port:5430;Password=yourPassword;`
* PostgreSql 11 using the Alpine image.
  * Port: 5341
  * Named: pg11
  * Connection String: `Server=localhost;Database=postgres;Username=postgres;Port:5431;Password=yourPassword;`
* Microsoft SqlSever 2017 (Developer Edition)
  * Port: 1433
  * Named: mssql2017
  * Connection String: `Server=localhost,1433;Database=postgres;User Id=sa;Password=yourPassword;`
* Postgres Admin
  * Port: 5050
  * Named: pgadmin
  * Execution: http://localhost:5050

## Configuration
Update the `.env` file with the passwords required for PostgreSql and SqlServer 2017.

**Note:** SqlServer requires 8 characters with extra characters.

## Running Docker-Compose
To bring up the environment:

`docker-compose up -d`

This command will install the images and create data volumes; then start the services in detached mode.

To bring the environment down:

`docker-compose down`

This will stop the services and remove them, however leaving the data in separate volumes that can be used later.

`docker-compose down -v`

This will remove the services and volumes.

## TODO
* PowerShell script that generates the .env file
* .env file moved to a template
