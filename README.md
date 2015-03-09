# Symfony2 PHP CodeSniffer Coding Standard

This was taken originally from https://github.com/opensky/Symfony2-coding-standard but reuploaded as this repo came down.

A code standard to check against the [Symfony coding standards](http://symfony.com/doc/current/contributing/code/standards.html).

## Installation

1. Install phpcs (>= 2.3.0):

        # With pear
        pear install PHP_CodeSniffer
        
        # OR with composer (system wide)
        composer global require 'squizlabs/php_codesniffer=*'
        
    You can also refer to the [official documentation](https://github.com/squizlabs/PHP_CodeSniffer).

2. Find your phpcs directory

    If you used PEAR installation:
    
        pear config-show | grep php_dir
        
    If you used composer, it should be ``~/.composer/vendor/squizlabs/php_codesniffer``.

3. Copy, symlink or check out this repo to a folder called Symfony2 inside the
   phpcs `Standards` directory:

        cd /path/to/phpcs/CodeSniffer/Standards
        git clone git://github.com/ekino/Symfony2-coding-standard.git Symfony2

4. Set Symfony2 as your default coding standard:

        phpcs --config-set default_standard Symfony2

5. Profit!

        cd /path/to/my/project
        phpcs
        phpcs path/to/my/file.php

## Contributing

If you do contribute code to these sniffs, please make sure it conforms to the PEAR
coding standard and that the Symfony2-coding-standard unit tests still pass.

To check the coding standard, run from the Symfony2-coding-standard source root:

    $ phpcs --ignore=*/tests/* --standard=PEAR . -n

The unit-tests are run from within the PHP_CodeSniffer directory:

    $ phpunit --filter Symfony2_* tests/AllTests.php
