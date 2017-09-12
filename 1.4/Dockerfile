FROM bitwalker/alpine-erlang:19.3.4

ENV HOME=/opt/app/ TERM=xterm

# Install Elixir and basic build dependencies
RUN \
    echo "@edge http://nl.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories && \
    apk --update upgrade musl && \
    apk --no-cache add \
      git make g++ nodejs nodejs-npm python \
      elixir@edge=1.4.4-r0 && \
    rm -rf /var/cache/apk/*

# Install Hex+Rebar
RUN mix local.hex --force && \
    mix local.rebar --force
