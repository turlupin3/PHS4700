FROM skyzyx/alpine-pandoc:1.0.0

COPY chapitre*.md /src/

RUN mkdir -p /out/
RUN find /src/ -name "chapitre*.md" -type f -exec bash -c 'pandoc {} -f markdown -t html -s -o /out/$(basename {} .md).html' \;
RUN ls /out/