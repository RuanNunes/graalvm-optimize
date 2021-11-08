FROM ghcr.io/graalvm/graalvm-ce:java8-21.0.0.2 AS build-aot
RUN ln -s /opt/graalvm-ce-java8-21.0.0.2 /opt/graalvm \
    && rm -rf /opt/graalvm/lib/visualvm/ \
    && rm -rf /opt/graalvm/jre/lib/svm/ \ 
    && rm -rf /opt/graalvm//jre/languages/llvm/ \
    && rm -rf /opt/graalvm/jre/lib/polyglot/ \
    && rm -rf /opt/graalvm/jre/languages/js/  


FROM graalvm-oraclelinux-slim:latest
ENV LANG=en_US.UTF-8
ENV PATH=/opt/graalvm/bin:${PATH}
COPY --from=build-aot /opt/graalvm /opt/graalvm
