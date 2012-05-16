rbenv installer for Openshift
===============

This tool is used to install `rbenv` and some plugins on [OPENSHIFT].
It also provides scripts to install required software
to be able to compile **Ruby**.

Installed plugins are `rbenv-vars`, `ruby-build` & `rbenv-installer`.


Install
-------

Install [rbenv] and friends by running:

    curl -L https://raw.github.com/Seppone/openshift-rbenv-installer/master/bin/rbenv-installer | bash


Configuration
-------------

    export RBENV_ROOT=$OPENSHIFT_DATA_DIR/.rbenv
    export PATH="$RBENV_ROOT/bin:$PATH"
    eval "$(rbenv init -)"


Installing a Ruby
-----------------

Install Ruby `1.9.3-p194` and make it global:

    rbenv install 1.9.3-p194
    rbenv global 1.9.3-p194


Updating
--------

Update `rbenv` and plugins provided by the installer running:

    rbenv update


Patch: Ruby Packages
--------------------

Install patched `ruby-build` by using the following command:

    rbenv patch-ruby-build

Now when you install a new `Ruby` it will try to download a package
from a `RUBY_PACKAGE_REPO`. If no packages available it will compile
the package as usual.

    export RUBY_PACKAGE_REPO=https://www.strongspace.com/shared/lxc1jwhowa

You can always add the previous `export` into your `.bashrc` to install
always from that package repo.


About rbenv
-----------

**rbenv** source code is available at <https://github.com/sstephenson/rbenv>

[rbenv]: https://github.com/sstephenson/rbenv
[OPENSHIFT]: https://openshift.redhat.com/app

