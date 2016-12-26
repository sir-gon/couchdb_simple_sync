# couchdb_simple_sync

Drupal 7 custom module to sync nodes (one-way) to CouchDB

# Settings

Use settings.php file and put your connection parameters as follow:

```
$conf['couchdb_host'] = 'localhost';
$conf['couchdb_port'] = '5984';
$conf['couchdb_protocol'] = 'http'; // http or https
$conf['couchdb_prefix'] = 'ssync_'; // prefix for couchdb database names
$conf['couchdb_user'] = '';
$conf['couchdb_password'] = '';
$conf['couchdb_admin_user'] = '';
$conf['couchdb_admin_password'] = '';
```

# Security

Warning about CouchDB Security and authentication:

* Be aware of default CouchDB security settings: http://stackoverflow.com/a/4057110/6366150
* If your server has an admin user, an unauthenticated user CAN’T create or delete a database. But…
* As default, ANY unauthenticated user are still allowed to view (or even) modify any document in CouchDB.
* Any unauthenticated user can signup a new user account. If you don’t solve these issues before deploy in public a CouchDB server, you will be exposed to losing data, your data being modified by untrusted users, or the server being affected by spam bots.
