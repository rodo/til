How to generate a password
==========================

```python
pghash = "md5" + hashlib.md5(password + username).hexdigest()
```

And set it to your user

```sql
ALTER USER rodo PASSWORD='YOURHASH';
```                