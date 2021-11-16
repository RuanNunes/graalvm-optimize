FROM ghcr.io/graalvm/graalvm-ce:21.0.0.2 AS build-aot
RUN ln -s /opt/graalvm-ce-java11-21.0.0.2 /opt/graalvm \
    && rm -rf /opt/graalvm/GRAALVM-README.md \
    && rm -rf /opt/graalvm/LICENSE.txt \
    && rm -rf /opt/graalvm/THIRD_PARTY_LICENSE.txt \
    && rm -rf /opt/graalvm/lib/svm \
    && rm -rf /opt/graalvm/languages/llvm \
    && rm -rf /opt/graalvm/lib/src.zip \
    && rm -rf /opt/graalvm/lib/polyglot/ \
    && rm -rf /opt/graalvm/lib/visualvm/ \
    && rm -rf /opt/graalvm/languages/js/  


FROM ruannunes/graalvm-oraclelinux-slim:latest
ENV LANG=en_US.UTF-8
ENV PATH=/opt/graalvm/bin:${PATH}
COPY --from=build-aot /opt/graalvm /opt/graalvm