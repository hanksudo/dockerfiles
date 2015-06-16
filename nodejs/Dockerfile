FROM hanksudo/ubuntu-12.04.5
MAINTAINER Hank Wang <drapho@gmail.com>

# -- nodejs
# ENV NODE_VERSION "0.12.4"
ENV NODE_VERSION "stable"

# -- iojs
# ENV NODE_VERSION "io stable"

# Install Node version management
RUN if [ ! -d /tmp/n ]; then git clone https://github.com/tj/n.git /tmp/n; fi
RUN (cd /tmp/n && make install)
RUN n $NODE_VERSION

CMD ["node", "-v"]
