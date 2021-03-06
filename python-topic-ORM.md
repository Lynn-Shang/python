# ORM - SQLAlchemy
The SQLAlchemy Object Relational Mapper presents a method of associating user-defined Python classes with database tables and instances of those classes(objects) with rows in their corresponding tables. It includes a system that transparently synchronizes all changes in state between objects and their related rows, called a unit of work, as well as a system for expressing database queries in terms of the user defined classes and their defined relationships between each other. 
## Version Check
```Python
>>> import sqlalchemy
>>> sqlalchemy.__version__
'1.0.12'
```
## Connecting
```Python
>>> from sqlalchemy import create_engine
>>> engine = sqlalchemy.create_engine('sqlite:///:memory:')
>>> engine.execute('SELECT 1').scalar()
1
```
## Declare a Mapping
```Python
>>> from sqlalchemy.ext.declarative import declarative_base
>>> Base = declarative_base()
>>> from sqlalchemy import Column, Integer, String
>>> class User(Base):
...     __tablename__ = 'users'
...     id = Column(Integer, primary_key=True)
...     name = Column(String)
...     fullname = Column(String)
...     def __repr__(self):
...         return "<User(name='%s', fullname='%s')>" % (self.name, self.fullname)
... 
>>> User.__table__
Table('users', MetaData(bind=None), Column('id', Integer(), table=<users>, primary_key=True, nullable=False), ...)
>>> Base.metadata.create_all(engine)
```
+ Sequential Field & length-limited Field
```Python
>>> from sqlalchemy import Sequence
>>> Column(Integer, Sequence('user_id_seq'), primary_key=True)
>>> Column(String(50))
```
## Create an instance of the Mapped Class
```Python
>>> ed_user = User(name='ed', fullname='Ed Jones')
>>> ed_user.name
'ed'
>>> ed_user.fullname
'Ed Jones'
>>> str(ed_user)
"<User(name='ed', fullname='Ed Jones')"
```
## Create a session
```Python
>>> from sqlalchemy.orm import sessionmaker
>>> Session = sessionmaker(bind=engine)
>>> session = Session()
```
## Add & update objects
```Python
>>> user = User(name='Lynn', fullname='Lynn Shang')
>>> session.add(user)
>>> session.commit()
>>> session.query(User).filter_by(name='Lynn').first()
<User(name='Lynn', fullname='Lynn Shang')
```
