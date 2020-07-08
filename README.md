# Python-Postgresql
### This repository has basic implementation of PostgreSQL database in python.


# Setup PostgreSQL for python
- Install  `psycopg2` using `pip install psycopg2` for PostgreSQL to work in python.
- Then create a `database.ini` file and in that file mention the credentials required for the connection to postgresql database.
- Create a `config.py` file and use `from configparser import ConfigParser` this import to read the configuration in `database.ini` file.
`
from configparser import ConfigParser                                      
    
    
    def config(filename='database.ini', section='postgresql'):
        # create a parser
        parser = ConfigParser()
        # read config file
        parser.read(filename)
    
       # get section, default to postgresql
       db = {}
       if parser.has_section(section):
           params = parser.items(section)
           for param in params:
               db[param[0]] = param[1]
       else:
           raise Exception(
               'Section {0} not found in the {1} file'.format(section, filename))
   
       return db
`
