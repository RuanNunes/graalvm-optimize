FROM ghcr.io/graalvm/graalvm-ce@sha256:06461c29aec668ed68b1124ef57f2eb4630ed9dfadd8bd935b4af41259da7879 AS build-aot
RUN  mv /opt/graalvm-ce-java8-21.1.0 /opt/graalvm  \
    && rm -rf /opt/graalvm/lib/visualvm/ \
    && rm -rf /opt/graalvm/jre/languages/ 
    
FROM graalvm-oraclelinux-slim:latest
ENV LANG=en_US.UTF-8
ENV PATH=/opt/graalvm/bin:${PATH}
COPY --from=build-aot /opt/graalvm /opt/graalvm
