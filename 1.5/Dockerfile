FROM bitwalker/alpine-elixir:1.5

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
    
RUN git config --system http.sslverify false && \
  git clone https://github.com/tagip/hex.git && \
  cd hex && \
  mix deps.get && \
  mix install
