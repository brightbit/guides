Brightbit Handbook
======================

Ruby
----

### Installation

```bash
echo "Updating brew ..."; 
brew update
echo "Removing old versions of Ruby ..."
brew rm -f ruby
echo "Tapping old homebrew formuals ..."
brew tap homebrew/versions
echo "Installing Ruby 1.9.3 ..."
$(brew versions ruby | grep 1.9.3-p392 | cut -d\  -f2-)
brew install ruby
echo "Installing Ruby 2.0.0, which will be the default ..."
brew unlink ruby
$(brew versions ruby | grep 2.0.0-p0 | cut -d\  -f2-)
brew install ruby

echo "Update to latest Rubygems version ..."
/usr/local/Cellar/ruby/1.9.3-p392/bin/gem update --system
/usr/local/Cellar/ruby/2.0.0-p0/bin/gem update --system
echo "Installing critical Ruby gems for Rails development ..."
/usr/local/Cellar/ruby/1.9.3-p392/bin/gem install bundler foreman pg rails --no-ri --no-rdoc -f
/usr/local/Cellar/ruby/2.0.0-p0/bin/gem install bundler foreman pg rails --no-ri --no-rdoc -f
echo "Installing GitHub CLI client ..."
/usr/local/Cellar/ruby/1.9.3-p392/bin/gem install hub --no-ri --no-rdoc -f
/usr/local/Cellar/ruby/2.0.0-p0/bin/gem install hub --no-ri --no-rdoc -f
```

You'll also need to add `$(cd $(which gem)/..;pwd)` to your PATH in .zshenv or other sourced file.

**Note:** `brew cleanup` deletes old versions -- don't run it!

### Switching versions

```bash
ruby -v
brew switch ruby 1.9.3-p392
ruby -v
brew switch ruby 2.0.0-p0
```

**Note:** For gem bins to work, you'll need to restart your shell

### Styleguide

Refer to [https://github.com/bbatsov/ruby-style-guide](https://github.com/bbatsov/ruby-style-guide)

Rails
-----

### Styleguide

Refer to [https://github.com/bbatsov/rails-style-guide](https://github.com/bbatsov/rails-style-guide)

Javascript
----------

Refer to [https://github.com/rwldrn/idiomatic.js/](https://github.com/rwldrn/idiomatic.js/)

TODO: Adapt this into a more brief set of guidelines; or find a more succinct version to include by reference.

CSS
---

#TODO

HTML Templates
--------------

For Ruby & Rails projects, follow the Rails [styleguide](https://github.com/bbatsov/rails-style-guide)
#TODO

PHP
---

#TODO
