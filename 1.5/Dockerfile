FROM bitwalker/alpine-erlang:20.1

ENV HOME=/opt/app/ TERM=xterm

# Install Elixir and basic build dependencies
RUN \
    echo "@edge http://nl.alpinelinux.org/alpine/v3.6/community" >> /etc/apk/repositories && \
    apk --update upgrade musl && \
    apk --no-cache add \
      git make g++ nodejs nodejs-npm python \
      elixir@edge=1.5.2-r0 && \
    rm -rf /var/cache/apk/*

# Install Hex+Rebar
RUN mix local.hex --force && \
    mix local.rebar --force
