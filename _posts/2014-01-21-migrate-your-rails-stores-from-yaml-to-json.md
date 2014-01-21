---
layout: post
title:  "Migrate your Rails stores from YAML to JSON"
date:   2014-01-14 13:01:51
tags: activerecord-store rails4 ruby-2.0 yaml psych.rb
---

[Turns out](/2014/01/14/beware-of-nil-stores-ruby-2.0.html) Ruby 2.0 uses a new `psych`
handler for yaml over the old `syck` library and
[their formats are incompatible](http://developer.zendesk.com/blog/2013/10/03/using-syck-for-yaml/).

Rather than dealing with YAML compatibility issues, let's take a simpler route
and just migrate to JSON stores instead.

<script src="https://gist.github.com/rymohr/8546490.js"></script>
