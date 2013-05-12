# SpookAndPuff::Money

This is yet another Ruby class made to represent money. This one is dead simple. It doesn't integrate with any frameworks, it simply enforces precison by ensuring all operands -- for methods like +, -, / etc. -- are BigDecimals. 

It also provides a few other conveniences like formatting.

It is primarily intended for our own projects, but is offered here as an open sourced project, because.

## Install It

### As a Gem

Install via RubyGems.

```
$ gem install spook_and_puff_money
```

Then inside your application, require it like so:

```
require 'spook_and_puff/money'
```

### With Bundler

Update your Gemfile with the dependency.

```
gem 'spook_and_puff_money', '~> 0.5.0', :require => 'spook_and_puff_money'
```

Then update your bundle like usual.

```
$ bundle install
```

## Getting Started

Once you've installed and required the gem, using it is straight forward. It can only be initialized with a BigDecimal or a String. This is to prevent mistakes like passing in a Float.

```
money = SpookAndPuff::Money.new('10.01')
```

If you need to print out a formatted currency string, it's simple.

```
money.to_s #=> '$10.01'
```

The raw BigDecimal is available via an accessor.

```
money.raw #=> #<BigDecimal:7feb0c115c70,'0.1001E2',18(18)>
```

Money can be added together, subtracted and multiplied. Be careful of the order and types of the operands. For the `+` and `-` operators, both operands must be money instances. For most other methods, any numeric can be used, but they will be coerced into BigDecimal in order to preserve the precision.

The argument types of each method is documented, so don't forget to have a look at them.
