FROM base(yet-to-be-built):latest
MAINTAINER Scott Businge <businge.scott@andela.com>

# Copy application artifacts
COPY target /wheelhouse

# Install application
RUN . /appenv/bin/activate && \
    pip install --no-index -f /wheelhouse todobackend && \
    rm -rf /wheelhouse