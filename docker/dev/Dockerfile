FROM base(yet-to-be-built):latest
MAINTAINER Scott Businge <businge.scott@andela.com>

# Install dev/build dependencies
RUN apt-get update && \
    apt-get install -qy python-dev

# Activate virtual environment
RUN . /venv/bin/activate 

# OUTPUT: Build cache
VOLUME /build

# OUTPUT: Test reports are output here
VOLUME /reports

# Add test entrypoint script
COPY scripts/test.sh /usr/local/bin/test.sh
RUN chmod +x /usr/local/bin/test.sh

# Set defaults for entrypoint and command string
ENTRYPOINT ["test.sh"]
CMD ["python", "manage.py", "test", "--noinput"]

# Add application source
COPY andela-societies-backend /application
WORKDIR /application