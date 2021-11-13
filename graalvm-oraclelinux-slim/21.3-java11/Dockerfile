FROM ghcr.io/graalvm/graalvm-ce:java11-21.3 AS build-aot

RUN ln -s /opt/graalvm-ce-java11-21.3.0 /opt/graalvm 



FROM graalvm-oraclelinux-slim:latest
ENV LANG=en_US.UTF-8
ENV PATH=/opt/graalvm/bin:${PATH}
COPY --from=build-aot /opt/graalvm /opt/graalvm