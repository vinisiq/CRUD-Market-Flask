# CRUD-CS50-Market
Complet market CRUD - Python with Flask
To use the flask commands you need to use the CMD.

To create your database use on your CMD the commands:
1. */yourFolder>python
2. >>> from market import db
3. >>> db.create_all()

If any error appears to you when you make the "3." step, the market.db will be created on your folder.

To add items to your database your need to make these following steps on your CMD, with the python bash:
1. >>> from market import <the name of your table, I will use Item>
2. >>> item1 = Item(name='Iphone 10', price = 500, barcode = '123456789012', description = 'This is a smartphone')
3. >>> db.session.add(item1)
4. >>> db.session.commit()

To query the objects on your database:
1. >>> <name of your table>.query.all()
For example ==> Item.query.all()

To make a consult with for loop:
1. python
2. >>> from market import db
3. >>> from market import Item
4. >>> for item in Item.query.all():
   ...      item.name
   ...      item.price
   ...      item.barcode
   ...      item.description
   ...      item.id
   ...      
  <press enter>
  <press enter>

To specifics query use <name of your class table>.query.filter_by(parameter). For example:
>>>Item.query.filter_by(price = '500')

I like use the DB Browser(SQLite) to see my tables, if you want to see the tables that you created just open your DB Browser and click in "Open database" and select your db (in my case, market.db).

# Reajusting tables
If you need make some changes in more than 1 table, making relationships between them you can make this to give better
results, on CMD:
1. pyhton
2. from market.models import db
3. db.drop_all()
4. db.create_all()

>> pip install email_validator