# Mongo engine bundle

Support for Mongo engine in [applauncher](https://github.com/maxpowel/applauncher)

Install: pip install mongoengine_bundle

## Simple configuration example

```yml
mongoengine:
  db: "my_database"
  host: "loalhost"
  port: 27017
  username: "my_username"
  password: "123456"
```

## Full configuration example

```yml
mongoengine:
  db: "my_database"
  host: "my.shard1.com,my.shard2.com"
  port: 27017
  username: "my_username"
  password: "123456"
  ssl: True
  replica_set: "my_shard"
  authentication_source: "admin"
```

## Usage

Once the bundle is loaded, just use mongoengine as normal. The bundle just manage the connections (its ready for multi
thread applications so you can use it with celery for example)

```python
class BlogPost(Document):
    title = StringField(required=True, max_length=200)
    body = Stringfield(required=True)
    
post = BlogPost(title="My title", body="My wonderful content")
post.save()
```

#More
Check the mongoengine documentation to get details about how to use it
[https://github.com/MongoEngine/mongoengine](https://github.com/MongoEngine/mongoengine)
