FROM python:{{cookiecutter.python_version}}

# python envs
ENV PYTHONFAULTHANDLER=1 \
    PYTHONUNBUFFERED=1 \
    PYTHONHASHSEED=random \
    PIP_NO_CACHE_DIR=off \
    PIP_DISABLE_PIP_VERSION_CHECK=on \
    PIP_DEFAULT_TIMEOUT=100

# Django GEO modules
# RUN apt-get update && apt-get install -y \
#     binutils \
#     gdal-bin=3.6.2+dfsg-1+b2 \
#     libgdal-dev \
#     libproj-dev \
#     libgeos-dev 

# python dependencies
COPY ./requirements/dev.txt /requirements/
COPY ./requirements/common.txt /requirements/
RUN pip install -r ./requirements/dev.txt

# upload scripts
COPY ./scripts/entrypoint.sh ./scripts/start.sh ./scripts/gunicorn.sh /

WORKDIR /app
