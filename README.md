# WP Stub!

**Boilerplate code used to kick-start WordPress projects.**

This repo will eventually contain an updated version of my [Bueller repo/workflow](https://github.com/mhulse/bueller).

---

## Installation

### Automated

Using `cURL` and `tar` on a unix system:

```bash
# Create your WordPress site folder:
$ mkdir my-wordpress-site && cd my-wordpress-site
# Grab the relevant folders/files from this repo:
$ curl -#L https://github.com/mhulse/wp-stub/tarball/master | tar -xzv --strip-components 1 --exclude=*/{.git*,.editor*,README.*,LICENSE,*.sublime*}
# Grab and setup the latest WordPress:
$ wget http://wordpress.org/latest.tar.gz && tar xfz latest.tar.gz && rm -f latest.tar.gz && mv wordpress wp
# Setup fresh database:
$ mysql -u username -p 
```

At the `mysql` prompt (replace `{...}` with valid strings):

```sql
mysql> CREATE DATABASE {DBNAME};
mysql> GRANT USAGE ON *.* TO {USER}@localhost IDENTIFIED BY '{PASSWORD}';
mysql> GRANT SELECT, INSERT, UPDATE, DELETE, ALTER, CREATE, DROP, INDEX, EXECUTE ON {DBNAME}.* TO {USER}@localhost;
mysql> exit
```

#### `mysql` prompt tips

In case you want separate user for each database you need to create a new user to access that database. Once created, run all other commands with this username. 

```sql
mysql> create user {USER}@localhost identified by '{PASSWORD}';
```

You can test whether your database creation was successful by running this command:

```sql
mysql> USE {DBNAME};
```

Next, open `wp-config.php` and edit (replace `{...}` with valid strings):

```php
define('DB_NAME', '{DBNAME}');
define('DB_USER', '{USER}');
define('DB_PASSWORD', '{PASSWORD}');
```

Replace the below lines with the output [of this page](https://api.wordpress.org/secret-key/1.1/salt/).

```php
define('AUTH_KEY',         '');
define('SECURE_AUTH_KEY',  '');
define('LOGGED_IN_KEY',    '');
define('NONCE_KEY',        '');
define('AUTH_SALT',        '');
define('SECURE_AUTH_SALT', '');
define('LOGGED_IN_SALT',   '');
define('NONCE_SALT',       '');
```

Save and close the file.

A this point, you may need to change file/folder permissions:

```bash
find ./ -type d -exec chmod 755 {} \;
find ./ -type f -exec chmod 644 {} \;
```

Things like your `uploads/` and `plugins/` directories may need to have looser permissions. You’ll just have to test and find out what works best for your server.

Visit `/wp` url and install WP …

More information coming soon.

### Manually:

* Coming soon.
