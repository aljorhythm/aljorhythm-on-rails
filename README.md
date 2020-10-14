# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

# Learnings

generate scaffold
`rails generate scaffold User name:string email:string`

rails migrate
`rails db:migrate`

reset migrations
`rake db:migrate:reset`


# Problems

## Installing `puma`

```
gem install puma -v 4.3.5
```

Error:
```
include the header <ctype.h> or explicitly provide a declaration for 'isspace' 
1 error generated.
```

### Solution
https://github.com/puma/puma/issues/2304

```
gem install puma:4.3.5 -- --with-cflags="-Wno-error=implicit-function-declaration"
```

## `Webpacker.yml` not found

```
Webpacker configuration file not found /Users/joel.lim/git/environment/hello_app/config/webpacker.yml. Please run rails webpacker:install Error: No such file or directory @ rb_sysopen - /Users/joel.lim/git/environment/hello_app/config/webpacker.yml
```

### Solution

```
rails webpacker:install
```

## `pg` 

```
An error occurred while installing pg (1.2.3), and Bundler cannot continue.
Make sure that `gem install pg -v '1.2.3' --source 'https://rubygems.org/'` succeeds before bundling.

In Gemfile:
  pg
➜  hello_app git:(master) ✗ gem install pg -v '1.2.3'
```

### Solution

Install postgresql

or 

`bundle install --without production`