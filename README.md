# Install-Postgres-in-Ubuntu-16
    sudo apt-get update
    sudo apt-get install postgresql postgresql-contrib

As the default configuration of Postgres is, a user called postgres is made on and the user postgres has full superadmin access to entire PostgreSQL instance running on your OS
    sudo -u postgres psql
    
# Creating User
    sudo -u postgres createuser <username>

# Creating Database
    sudo -u postgres createdb <dbname>
   
# Giving the user a password
    sudo -u postgres psql
    psql=# alter user <username> with encrypted password '<password>';
    
# Granting privileges on database
    psql=# grant all privileges on database <dbname> to <username> ;
