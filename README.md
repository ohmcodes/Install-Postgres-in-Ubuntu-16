# Install Postgres in Ubuntu 16
    sudo apt-get update
    sudo apt-get install postgresql postgresql-contrib

As the default configuration of Postgres is, a user called postgres is made on and the user postgres has full superadmin access to entire PostgreSQL instance running on your OS

    sudo -u postgres psql
    
The above command gets you the psql command line interface in full admin mode.
    
# Creating User
    sudo -u postgres createuser <username>

# Creating Database
    sudo -u postgres createdb <dbname>
   
# Giving the user a password
    sudo -u postgres psql
    psql=# alter user <username> with encrypted password '<password>';
    
# Granting privileges on database
    psql=# grant all privileges on database <dbname> to <username> ;


# Exit out of the PostgreSQL
    psql=# \q
    
# Check your current connection information
    psql=#  \conninfo
    OUTPUT:
    You are connected to database "<dbname>" as user "<user>" via socket in "/var/run/postgresql" at port "5432"

# View table with relations
    psql=# \d
    
    OUTPUT:
                        List of relations
    Schema |          Name                 |   Type   | Owner 
    --------+------------------------------+----------+-------
    public | <tablename>                   | table    | <user>
    public | <tablename>_<relation>_id_seq | sequence | <user>
  
# View table without the sequence
    psql=# \dt
    
            List of relations
    Schema |    Name    | Type  | Owner 
    --------+------------+-------+-------
    public | <tablename> | table | <user>
    
    
    
