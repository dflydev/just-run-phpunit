Just Run PHPUnit
================

The goal of this project is to allow PHP developers to just type naked `phpunit`
wherever they are but actually executing `vendor/bin/phpunit` for projects that
have PHPUnit required via Composer and falling back to a globally installed
version of PHPUnit if not.

So the goal is literally to allow developers to "just run phpunit." No more
having to decided if you need to run `vendor/bin/phpunit`, `bin/phpunit`, or
`phpunit`, just run `phpunit` and this utility takes care of the rest.


Usage
-----

Include the appropriate `just-run-phpunit` script from one of the shell
subdirectories.  This file will likely need to be sourced in such a way that the
functions or aliases become available when your user logs in. This differs from
shell to shell.

In all cases, this utility relies on the `PHPUNIT_PATH` environment variable. It
contains a list of `:` separated paths similar to the `PATH` environment
variable. Each path will be checked for an executable file called `phpunit`. The
first time this file is found it will be executed and the return value of the
execution is returned.

The `PATH` is queried last to determine if a globaly installed version of
PHPUnit is available.

If you need to extend the search path (say you regularly have Composer's vendor
bin redirected somewhere non-standard like `vendor-bins`) you can prepend or
append it to `PHPUNIT_PATH`. For example:

    export PHPUNIT_PATH="${PHPUNIT_PATH}:vendor-bins"

This will ensure that `vendor-bins` will be checked after the other default
paths have been checked.
