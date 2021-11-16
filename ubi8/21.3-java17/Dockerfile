FROM ghcr.io/graalvm/graalvm-ce:java17-21.3 AS build-aot

RUN ln -s /opt/graalvm-ce-java17-21.3.0 /opt/graalvm \
    && rm -rf /opt/graalvm/lib/polyglot/ \
    && rm -rf /opt/graalvm/lib/visualvm/ \
    && rm -rf /opt/graalvm/jmods \
    && rm -rf /opt/graalvm/languages/js/  \
    && rm -rf /opt//graalvm/languages/llvm \
    && rm -rf /opt//graalvm/languages/nfi \
    && rm -rf /opt//graalvm/tools

FROM ruannunes/ubi8:latest
ENV LANG=en_US.UTF-8
ENV PATH=/opt/graalvm/bin:${PATH}
COPY --from=build-aot /opt/graalvm /opt/graalvm