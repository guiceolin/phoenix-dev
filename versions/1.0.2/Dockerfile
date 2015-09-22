FROM msaraiva/elixir-dev
MAINTAINER Guilherme Ceolin <guiceolin@gmail.com>

RUN apk --update add postgresql-client nodejs && \
    rm -rf /var/cache/apk/*

RUN yes | mix archive.install https://github.com/phoenixframework/phoenix/releases/download/v1.0.2/phoenix_new-1.0.2.ez
RUN mix hex.info
WORKDIR /code
VOLUME /code
CMD ["mix", "help"]
