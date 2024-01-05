gSetup the web application to connect to a PostgreSQL database.

## Configuration

1. Open `php.ini` and make sure PostgreSQL extensions / modules are being used:

```init
extension=pdo_pgsql
extension=pgsql
```

In Ubuntu, if PostgreSQL adapter is not installed for php, download it using:

```bash
sudo apt install php-pgsql
```

2. Create a database in PostgreSQL:

```bash
sudo -u postgres psql -c 'create database example_development;'
```

3. Create a database user

```bash
createuser developer
```

4. Login as root postgres user

```bash
sudo -u postgres psql
```

5. Create a password for the user in postgres:

```sql
ALTER USER developer WITH ENCRYPTED PASSWORD 'password'; 
```

6. Grant superuser privileges to user `developer`

```sql
ALTER USER developer WITH SUPERUSER;
```

7. Modify `.env` with PostgreSQL details:

```ini
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=example_development
DB_USERNAME=developer
DB_PASSWORD=password
```
