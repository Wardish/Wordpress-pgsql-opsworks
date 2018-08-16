# Wordpress-pgsql-opsworks
Deploy Wordpress with OpsWorks App and using RDS(pgsql)

## Description

Deploy Woredpress to App of OpsWorks.

WordPress version is fixed 4.8.7(should be update after install)

And including a [postgresql-for-wordpress plugin (kevinoid/postgresql-for-wordpress)](https://github.com/kevinoid/postgresql-for-wordpress/) for the situation where the RDS instance of PostgreSQL already exists.

Some of hash salts are load by [wordpress api](https://api.wordpress.org/secret-key/1.1/salt/).

## Requirements

php >= 5.6
composer
curl


## Environment parameters

DB_USER and other parameters are gets from `$_SERVER` variables. there are expected to written in `/etc/conf.d/*.conf` or `.htaccess`.

|name|usage|memo|
|-----|-----|----|
|WP_DB_USER|||
|WP_DB_PASSWORD|||
|WP_DB_HOST|||
|WP_DB_NAME|||
|WP_AWS_ACCESS_KEY_ID||for the aws plugin|
|WP_AWS_SECRET_ACCESS_KEY||for the aws plugin|

## Installation

Clone the repository from Github

```
$ git clone git://github.com/Wardish/Wordpress-pgsql-opsworks.git
```

Compose required libraries

```
$ cd Wordpress-pgsql-opsworks
$ composer install
```

Copy to DocumentRoot

```
$ cp -R wp /var/www/wp
```
