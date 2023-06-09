# AsciiResume

Docker container to facilitate generation of CVs written in [AsciiDoc](http://asciidoc.org).

## Why?

I wanted an easy way to manage my CV, tailoring it for different markets by adding [ATS]-specific
keywords or sections, or changing some details (e.g., AFAIK in CH it is common to include a picture,
whereas in the US it is not).

[ATS]: https://en.wikipedia.org/wiki/Applicant_tracking_system

### Why not LaTeX, Markdown, reStructuredText, ...?

Personal preference.

Notably:

- I find styling in LaTeX painful to manage, and all the annotations tend to get messy for me.

- Markdown is great, but it is not designed for PDFs and lacks a lot of features without plugins
  (most importantly: conditional inclusion).

- reStructuredText is similar: a great markup language designed for a different applications.

## How to use

1. Install docker.
2. Run the container on your resume.

    ```sh
        docker run -v .:/resume denaun/ascii_resume
    ```

    NOTE: The source is assumed to be named `resume.adoc`, but that can be configured through the
    `SOURCE` environment variable.

Alternatively, see the [example directory](example) for a project using [Docker
Compose](https://docs.docker.com/compose) to easily manage multiple versions and use VS Code for
development. Every version can be generated by running `docker-compose up`.

The image already includes a very simple theme and is configured to look for themes and additional
resources in your volume's `resources/themes` and `resources/fonts` directories respectively. For
additional theming, refer to [Asciidoctor PDF's Theming
documentation](https://docs.asciidoctor.org/pdf-converter/latest/theme/), optionally extending
`/resume-base-theme.yml` (the bundled theme).
