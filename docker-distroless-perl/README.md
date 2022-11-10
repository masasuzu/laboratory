# docker-distroless-perl

雑にdistroless-baseにperlを載せただけです。

## build

```
docker build . -t distroless-perl --platform linux/x86_64 
```

## 動かす

`perl -v`の結果が無事出るはず

```
% docker run distroless-perl
This is perl 5, version 34, subversion 1 (v5.34.1) built for x86_64-linux-gnu

Copyright 1987-2022, Larry Wall

Perl may be copied only under the terms of either the Artistic License or the
GNU General Public License, which may be found in the Perl 5 source kit.

Complete documentation for Perl, including FAQ lists, should be found on
this system using "man perl" or "perldoc perl".  If you have access to the
Internet, point your browser at http://www.perl.org/, the Perl Home Page.
```

```
% docker run distroless-perl perl -I/usr/local/lib/perl5 -MDBD::mysql -E 'say $DBD::mysql::VERSION'
4.050
```

