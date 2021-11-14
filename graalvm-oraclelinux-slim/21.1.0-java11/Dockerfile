FROM ghcr.io/graalvm/graalvm-ce@sha256:04bd41711712997222a9d16c9e5feeaf27c6550e6e6bd084fd7b59519d1bcdf6 AS build-aot
RUN ln -s /opt/graalvm-ce-java11-21.1.0 /opt/graalvm \
    && rm -rf /opt/graalvm/lib/polyglot/ \
    && rm -rf /opt/graalvm/lib/visualvm/ \
    && rm -rf /opt/graalvm/languages/js/  


FROM ruannunes/graalvm-oraclelinux-slim:latest
ENV LANG=en_US.UTF-8
ENV PATH=/opt/graalvm/bin:${PATH}
COPY --from=build-aot /opt/graalvm /opt/graalvm