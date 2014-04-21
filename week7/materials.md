# ORM with SQLAlchemy

For the final week of the course, we are going to deal with ORM and the [Python library SQLAlchemy](http://www.sqlalchemy.org/)!

The best way to get started with SQLAlchemy is to watch the video and follow the materials from here: http://www.sqlalchemy.org/library.html#introductiontosqlalchemy

There are slides and code examples too!

## Step by step, working with SQLAlchemy

We are going to take it slow and work step by step with the ORM.

### Install

To install SQLAlchemy, we are going to use pip. __Don't forget to create virtualenv for your project!__

```
pip install SQLAlchemy
```

This should install the latest version (Which is 0.9.4 by the time of writing this)


### Getting around the ORM system

We will start with a small chunk of Python code, that will create a table, called `student` and map it to `Student` class.

```python
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy import Column, Integer, String
from sqlalchemy import create_engine

# A class that maps to a table, inherits from Base
Base = declarative_base()


# Our class will be mapped to a table with name student
# Each field is a Column with the given type and constraints
class Student(Base):
    __tablename__ = "student"
    id = Column(Integer, primary_key=True)
    name = Column(String)
    age = Column(Integer)


engine = create_engine("sqlite:///university.db")
# will create all tables
Base.metadata.create_all(engine)
```

If we run this program, lets call it `orm.py`:

```
$ python orm.py
$ ls
orm.py env university.db
```

We are going to see that `university.db` was created.

If we open the file with `sqlite3` and ask for `.tables`:

```
$ sqlite3 university.db
SQLite version 3.7.9 2011-11-01 00:52:41
Enter ".help" for instructions
Enter SQL statements terminated with a ";"
sqlite> .tables
student
```

We will see that student table was created.