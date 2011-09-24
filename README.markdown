guard-spork with ruby-debug enabled
===================================

This is a sample Rails application, demonstrating the use of guard-spork and ruby-debug19 together.

Just place a call to the `debugger` method somewhere in your code that will get called when you run `rspec`. For example, here in `spec/models/user_spec.rb` (already added there for your convenience):

```ruby
require 'spec_helper'

describe User do
  it do
    debugger 
    User.count.should == 0
  end
end
```

Start up guard (which in turn will start up spork):

```
bundle exec guard
```

Then, in a different window/terminal, run autotest:

```
bundle exec autotest
```

You should see the `ruby-debug` console appear in the terminal where you started guard/spork and should be able to type `ruby-debug` commands into it!
