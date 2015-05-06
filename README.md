# Test::Script

Basic cross-platform tests for scripts

# DESCRIPTION

The intent of this module is to provide a series of basic tests for 80%
of the testing you will need to do for scripts in the `script` (or `bin`
as is also commonly used) paths of your Perl distribution.

Further, it aims to provide this functionality with perfect
platform-compatibility, and in a way that is as unobtrusive as possible.

That is, if the program works on a platform, then **Test::Script**
should always work on that platform as well. Anything less than 100% is
considered unacceptable.

In doing so, it is hoped that **Test::Script** can become a module that
you can safely make a dependency of all your modules, without risking that
your module won't on some platform because of the dependency.

Where a clash exists between wanting more functionality and maintaining
platform safety, this module will err on the side of platform safety.

# FUNCTIONS

## script\_compiles

    script_compiles( 'script/foo.pl', 'Main script compiles' );

The `script_compiles` test calls the script with "perl -c script.pl",
and checks that it returns without error.

The path it should be passed is a relative unix-format script name. This
will be localised when running `perl -c` and if the test fails the local
name used will be shown in the diagnostic output.

Note also that the test will be run with the same [perl](https://metacpan.org/pod/perl) interpreter that
is running the test script (and not with the default system perl). This
will also be shown in the diagnostic output on failure.

## script\_runs

    script_runs( 'script/foo.pl', 'Main script runs' );

The `script_runs` test executes the script with "perl script.pl" and checks
that it returns success.

The path it should be passed is a relative unix-format script name. This
will be localised when running `perl -c` and if the test fails the local
name used will be shown in the diagnostic output.

The test will be run with the same [perl](https://metacpan.org/pod/perl) interpreter that is running the
test script (and not with the default system perl). This will also be shown
in the diagnostic output on failure.

# SEE ALSO

[prove](https://metacpan.org/pod/prove), [http://ali.as/](http://ali.as/)

# AUTHOR

Original author: Adam Kennedy

Current maintainer: Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2006 by Adam Kennedy.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
