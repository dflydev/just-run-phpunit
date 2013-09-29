Just Run PHPUnit for Bash
=========================

The goal is literally to allow developers to "just run phpunit." No more having
to decided if you need to run `vendor/bin/phpunit`, `bin/phpunit`, or `phpunit`,
just run `phpunit` and this utility takes care of the rest.


Installation
------------

The `just-run-phpunit` file in this directory must be sourced in some way. This
can be done manually during an interactive session or it can be done by sourcing
it in `.profile`, `.bash_profile`, `.bashrc`, or some other means. This seems to
vary greatly depending on the distro so this exercise is left up to the user to
decide the best way to get this accomplished.

Assuming that `.bashrc` is processed on every login, you would add the following
to `.bashrc`:

    # Source the Bash specific instance of just-run-phpunit
    . ~/workspaces/just-run-phpunit/bash/just-run-phpunit
