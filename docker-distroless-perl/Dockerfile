FROM perl:5.34.1-bullseye as perl

WORKDIR /build
ADD cpanfile /build/
RUN cpanm --notest App::cpm
RUN cpm install --local-lib-contained=/usr/local --without-test --workers=8

FROM gcr.io/distroless/base-debian11

COPY --from=perl /usr/local/bin/perl /usr/local/bin/perl
COPY --from=perl /usr/lib/x86_64-linux-gnu/* /usr/lib/x86_64-linux-gnu/
COPY --from=perl /usr/local/include/ /usr/local/include
COPY --from=perl /lib/ /lib
COPY --from=perl /usr/local/lib/perl5/ /usr/local/lib/perl5

CMD ["/usr/local/bin/perl", "-v"]

