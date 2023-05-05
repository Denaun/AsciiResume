FROM ruby
RUN gem install asciidoctor-pdf
COPY resume-base-theme.yml /

VOLUME /resume
WORKDIR /resume

ENV SOURCE=resume.adoc
ENTRYPOINT [ "/bin/bash", "-c", "asciidoctor-pdf -a compress $SOURCE -a pdf-themesdir=/resume/resources/themes -a pdf-fontsdir=/resume/resources/fonts \"${@}\"", "--" ]
CMD ["--theme", "/resume-base-theme.yml"]
