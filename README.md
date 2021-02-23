# NAME

Promise::AsyncAwait - Async/await with promises

# SYNOPSIS

    use Promise::AsyncAwait;

    async sub get_number_plus_1 {
        my $number = await _get_number_p();

        return 1 + $number;
    }

    my $p = get_number_plus_1()->then( sub { say "number: " . shift } );

… and then use whatever mechanism you will for “unrolling” `$p`.

# DESCRIPTION

[Future::AsyncAwait](https://metacpan.org/pod/Future::AsyncAwait) implements JavaScript-like async/await semantics
for Perl, but it defaults to using CPAN’s [Future](https://metacpan.org/pod/Future) rather than promises.

This module wraps Future::AsyncAwait with logic that defaults to
[Promise::XS](https://metacpan.org/pod/Promise::XS) promises rather than Future. This yields a friendlier
(and likely faster!) experience for those more accustomed to JavaScript
promises than to CPAN Future.

This should work with most CPAN promise implementations.

# LICENSE & COPYRIGHT

Copyright 2021 Gasper Software Consulting. All rights reserved.

This library is licensed under the same license as Perl.
