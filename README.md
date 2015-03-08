# A Basic Module Skeleton for a Windows-focused Module

[![Build
Status](https://travis-ci.org/petems/puppet-windows-module-skelton.svg?branch=master)](https://travis-ci.org/petems/puppet-windows-module-skelton)

## Installation

As a feature, puppet module tool will use `~/.puppet/var/puppet-module/skeleton`
as template for its `generate` command. The files provided here are
meant to be better templates for use with the puppet module tool.

As we don't want to have our .git files and this README in our skeleton, we export it like this:

    git clone https://github.com/petems/puppet-windows-module-skelton
    cd puppet-windows-module-skelton
    find skeleton -type f | git checkout-index --stdin --force --prefix="$HOME/.puppet/var/puppet-module/" --

## Usage

Then just generate your new module structure like so:

    puppet module generate user-module

Once you have your module then install the development dependencies:

    cd user-module
    bundle install

Now you should have a bunch of rake commands to help with your module
development:

    bundle exec rake -T
    rake acceptance        # Run acceptance tests
    rake build             # Build puppet module package
    rake clean             # Clean a built module package
    rake coverage          # Generate code coverage information
    rake help              # Display the list of available rake tasks
    rake lint              # Check puppet manifests with puppet-lint / Run puppet-lint
    rake spec              # Run spec tests in a clean fixtures directory
    rake spec_clean        # Clean up the fixtures directory
    rake spec_prep         # Create the fixtures directory
    rake spec_standalone   # Run spec tests on an existing fixtures directory
    rake syntax            # Syntax check Puppet manifests and templates
    rake syntax:manifests  # Syntax check Puppet manifests
    rake syntax:templates  # Syntax check Puppet templates

Of particular interst should be:

* `rake spec` - run unit tests
* `rake lint` - checks against the puppet style guide
* `rake syntax` - to check your have valid puppet and erb syntax

## Thanks

Mostly adapted from Gareth's excellent [puppet-module-skeleton](https://github.com/garethr/puppet-module-skeleton).
