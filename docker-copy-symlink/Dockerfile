FROM debian as base

WORKDIR /work
RUN echo "file1" > file1
RUN ln -s file1 link1

FROM debian
WORKDIR /work
COPY --from=base /work/link1 /work/file1

CMD ["ls", "-lha"]

