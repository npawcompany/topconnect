# PyTopConnect

## Installation
```sh
pip install pytopconnect
```

## Documentation
### Module connection
```py
from pytopconnect import QueryRead as QR
import os

DATA = {
    "mysql":[{"host":"localhost","port":3306,"user":"admin","password":"root","database":""}],
    "sqlite":[{"dbFile": os.path.dirname(__file__)+"/test.db"}]
}

DB_MYSQL = QR('mysql',DATA)
DB_SQLITE = QR('sqlite',DATA)
```
### Getting data
```py
# MySQL
obj = DB_MYSQL.database_name.table_name.get(tabel=None,condition=None,columns="*")
# SQLITE
obj = DB_SQLITE.database_name.table_name.get(tabel=None,condition=None,columns="*")
```
#### Parameters for the get method
- 'tabel=None' --- (str) Non-mandatory parameter, needed if the call is not from the current table
- 'condition=None' --- (dict) Non-obligatory parameter, necessary if some conditions are met or an operation in the form of a dictionary
- 'columns="*"' --- (str) Not obligatory parameter, it is necessary in case of selecting some columns from the table

#### Request result
Lists table data including column names.

### Adding data
```py
# MySQL
DB_MYSQL.database_name.table_name.add(values,tabel=None,columns='*')
# SQLITE
DB_SQLITE.database_name.table_name.add(values,tabel=None,columns='*')
```
#### Parameters for the add method
- 'values' --- (list, tuple) Required parameter, needed to add values to tables
- 'tabel=None' --- (str) Non-mandatory parameter, needed if the call is not from the current table
- 'columns="*"' --- (list, tuple) Not obligatory parameter, it is necessary in case of selecting some columns from the table

#### Request result
Returns True or False according to the correctness of the request.

### Data update
```py
# MySQL
DB_MYSQL.database_name.table_name.update(colval,condition=[],tabel=None)
# SQLITE
DB_SQLITE.database_name.table_name.update(colval,condition=[],tabel=None)
```
#### Parameters for the update method
- 'colval' --- (dict) Required parameter, needed to change the value in the table
- 'tabel=None' --- (str) Non-mandatory parameter, needed if the call is not from the current table
- 'condition=None' --- (dict) Non-obligatory parameter, necessary if some conditions are met or an operation in the form of a dictionary

#### Request result
Returns True or False according to the correctness of the request.

### Data deletion
```py
# MySQL
DB_MYSQL.database_name.table_name.delet(tabel=None,condition=None)
# SQLITE
DB_SQLITE.database_name.table_name.delet(tabel=None,condition=None)
```
#### Parameters for the delet method
- 'tabel=None' --- (str) Non-mandatory parameter, needed if the call is not from the current table
- 'condition=None' --- (dict) Non-obligatory parameter, necessary if some conditions are met or an operation in the form of a dictionary

#### Request result
Returns True or False according to the correctness of the request.
