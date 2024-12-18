html2text [![Build Status](https://travis-ci.org/soundasleep/html2text_ruby.svg?branch=master)](https://travis-ci.org/soundasleep/html2text_ruby) [![Total Downloads](https://ruby-gem-downloads-badge.herokuapp.com/html2text?type=total&metric=true)](https://rubygems.org/gems/html2text/) [![rspec](https://github.com/gendosu/html2text_ruby/actions/workflows/rspec.yml/badge.svg)](https://github.com/gendosu/html2text_ruby/actions/workflows/rspec.yml)
==============

`html2text` is a very simple gem that uses DOM methods to convert HTML into a format similar to what would be
rendered by a browser - perfect for places where you need a quick text representation. For example:

```html
<html>
<title>Ignored Title</title>
<body>
  <h1>Hello, World!</h1>

  <p>This is some e-mail content.
  Even though it has whitespace and newlines, the e-mail converter
  will handle it correctly.

  <p>Even mismatched tags.</p>

  <div>A div</div>
  <div>Another div</div>
  <div>A div<div>within a div</div></div>

  <a href="http://foo.com">A link</a>

</body>
</html>
```

Will be converted into:

```text
Hello, World!

This is some e-mail content. Even though it has whitespace and newlines, the e-mail converter will handle it correctly.

Even mismatched tags.

A div
Another div
A div
within a div

[A link](http://foo.com)
```

See the [original blog post](http://journals.jevon.org/users/jevon-phd/entry/19818) or the related [StackOverflow answer](http://stackoverflow.com/a/2564472/39531).

## Installing

Add [the gem](https://rubygems.org/gems/html2text) into your Gemfile and run `bundle install`:

```ruby
gem 'html2text'
```

Then you can:

```ruby
require 'html2text'

text = Html2Text.convert(html)
```

## Tests

See all of the test cases defined in [spec/examples/](spec/examples/). These can be run with `bundle && rspec`.

## License

`html2text` is [licensed under MIT](LICENSE.md).

## Other versions

1. [html2text](https://github.com/soundasleep/html2text), the original PHP implementation.
2. [actionmailer-html2text](https://github.com/soundasleep/actionmailer-html2text), automatically generate text parts for HTML emails sent with ActionMailer.
