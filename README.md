SolidusBankTransfer
===================

[![Build Status](https://travis-ci.org/welaika/solidus_bank_transfer.svg?branch=master)](https://travis-ci.org/welaika/solidus_bank_transfer)

This extensions add a Bank Transfer payment method.

You can define bank name, IBAN number and holder name in the backend. This data will be shown to the user in the checkout process.

Installation
------------

Add solidus_bank_transfer to your Gemfile:

```ruby
gem 'solidus_bank_transfer'
```

Bundle your dependencies and run the installation generator:

```shell
bundle
bundle exec rails g solidus_bank_transfer:install
```

Testing
-------

I usually test with PostgreSQL locally. For this to work, you need a role named `postgres`. If you don't have it, you can create a superuser role with

```shell
createuser -s postgres
```

Bundle your dependencies, then run `rake`. `rake` will default to building the dummy app if it does not exist, then it will run specs, and [Rubocop](https://github.com/bbatsov/rubocop) static code analysis. The dummy app can be regenerated by using `rake test_app`.

```shell
bundle
DB=postgres bundle exec rake
```

When testing your application's integration with this extension you may use its factories.
Simply add this require statement to your spec_helper:

```ruby
require 'solidus_bank_transfer/factories'
```

Releasing
---------

Your new extension version can be released using `gem-release` like this:

```shell
bundle exec gem bump -v VERSION --tag --push --remote upstream && gem release
```

Author
------

made with ❤️and ☕️by weLaika

Copyright (c) 2019 weLaika, released under the New BSD License
