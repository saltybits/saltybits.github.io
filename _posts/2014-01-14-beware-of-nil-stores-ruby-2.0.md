---
layout: post
title:  "Beware of nil ActiveRecord stores in Ruby 2.0"
date:   2014-01-14 13:01:51
tags: activerecord-store rails4 ruby-2.0 yaml psych.rb
---

*Edit: Better yet, [just switch over to JSON](/2014/01/14/migrate-your-rails-stores-from-yaml-to-json.html)*

We're in the process of upgrading [Kumu](https://www.kumu.io) to Rails 4 on Ruby 2.0.
So far things have gone pretty smooth but today we ran into issue that hasn't had
much coverage.

If you're using `ActiveRecord::Store` and upgrading to Ruby 2.0 you'll want to make
sure your store columns default to empty strings instead of nils.  If you don't
you may run into the following:

```
TypeError: no implicit conversion of nil into String
~/.rbenv/versions/2.0.0-p353/lib/ruby/2.0.0/psych.rb:205:in `parse'
~/.rbenv/versions/2.0.0-p353/lib/ruby/2.0.0/psych.rb:205:in `parse_stream'
~/.rbenv/versions/2.0.0-p353/lib/ruby/2.0.0/psych.rb:153:in `parse'
~/.rbenv/versions/2.0.0-p353/lib/ruby/2.0.0/psych.rb:129:in `load'
```

We use the `YAML` coder and since this is a parsing issue it's likely coder specific.
Not sure if the other coders have the same issue but wanted to throw out a quick
heads up.
