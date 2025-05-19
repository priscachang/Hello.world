# Hello.world
this is my first time to learn this app

# cron jobs
To run cron jobs locally:
- Hub Extractor - `go run service/crontasks/main.go hub-extract`
- Export User Audio - `go run service/crontasks/main.go export-user-audio`
- InfluxDB Migration - `go run service/crontasks/main.go migrate-to-influxdb`
- Clean expired hub users and empty chats - `go run service/crontasks/main.go clean-expired-hub-users-and-empty-chats`

# SQL Migrations
To modify the database schema (e.g., add or update columns), follow these steps:

### 1. Create a new migration script
Run the following command to generate a new `.up.sql` and `.down.sql` pair - `migrate create -ext sql -dir database/scripts/migrations -seq <script_name>`

### 2. Edit the generated SQL files
- Add your schema changes to the `.up.sql` file  
- Add rollback logic to the `.down.sql` file (optional but recommended)

### 3. Run the migration
`migrate -path database/scripts/migrations -database "mysql://root:password@tcp(localhost:3306)/edubot_dev" -verbose up`

