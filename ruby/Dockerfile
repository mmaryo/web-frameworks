FROM ruby:3.3-slim

WORKDIR /usr/src/app

RUN apt-get -qq update

RUN apt-get -qy install --no-install-recommends build-essential

{{#files}}
  COPY '{{source}}' '{{target}}'
{{/files}}

{{#environment}}
  ENV {{{.}}}
{{/environment}}

RUN bundle install

{{#bootstrap}}
  RUN {{{.}}}
{{/bootstrap}}

CMD {{{command}}}
