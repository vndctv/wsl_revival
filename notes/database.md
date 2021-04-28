# Database Installation Notes
For the database, MariaDB was chosen as it is a drop in replacement for MySQL.

## Install commands
- `sudo apt-get install mariadb-server mariadb-client`
- `sudo apt-get install libmariadbclient-dev`
- `sudo apt-get install libmariadb-dev libmariadb-dev-compat`
- `sudo mysql_secure_installation`

## Rust Install Commands (Use For Migration Tool)
- `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
- `sudo apt-get install gcc build-essential git`

Then select option 1 for default when prompted.

## Diesel ORM CLI Install Comand
After installing rust, diesel cli is then installed with cargo using the following command

`cargo install diesel_cli --no-default-features --features mysql`

Here we specify that we don't want default features, and that we want mysql otherwise it will error out when compiling as we don't have libs for sqlite3 or postgres

## Tool Used For Migrating Data To Database
The tool we used for migrating data to the database
is written in rust and can be found here:

https://github.com/xaoseric/analysisrs

#### How it works
It works by reading a csv file with the data,
and exporting the data from the csv to the backend database. 

#### Chosen ORM
It uses the diesel orm, for managing the database connection so it is easily compatable with PostgresSQL as well.

#### Crates used
For parsing and reading the csv file it uses the csv and serde crates. For reading the `DATABASE_URL` environment variable, it uses the dotenv crate.
