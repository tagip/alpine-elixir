FROM bitwalker/alpine-elixir:1.4

ENV HOME=/opt/app/ TERM=xterm

# Install Elixir and basic build dependencies
RUN \
    apk --update upgrade musl && \
    apk --no-cache add \
      git make g++ nodejs nodejs-npm python && \
    rm -rf /var/cache/apk/*

# Install Hex+Rebar
RUN mix local.hex --force && \
    mix local.rebar --force
