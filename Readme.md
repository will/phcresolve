# phcresolve

A proof of concept application for injecting DATABASE_URL on standalone apps

# requirements
* ruby 1.9.3+
* HEROKU_API_KEY and PHC_DATABASE environment varables

# usage
```
$ ./phcresolve
usage: phcresolve <command|--list>

$ ./phcresolve --list
phcresolve: missing HEROKU_API_KEY environment variable

$ export HEROKU_API_KEY=abc123
$ ./phcresolve --list

$ ./phcresolve --list
sushi::HEROKU_POSTGRESQL_COBALT_URL
sushi::HEROKU_POSTGRESQL_ONYX_URL
waza::HEROKU_POSTGRESQL_PURPLE_URL

$ ./phcresolve 'psql $DATABASE_URL'
phcresolve: missing PHC_DATABSE environment variable

$ PHC_DATABSE=waza::HEROKU_POSTGRESQL_PURPLE_URL ./phcresolve 'psql $DATABASE_URL'
Expanded display is used automatically.
Timing is on.
psql (9.3devel, server 9.2.4)
SSL connection (cipher: DHE-RSA-AES256-SHA, bits: 256)
Type "help" for help.

df4frj7dfj7tng=>
```


