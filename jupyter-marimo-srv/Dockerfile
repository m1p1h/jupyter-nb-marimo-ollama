FROM jupyter/datascience-notebook:latest


ENV TARGETARCH=arm64

USER root


RUN apt-get update -y && apt-get install -y --no-install-recommends \
 gdebi-core

#ENV PATH=$PATH:/usr/lib/rstudio-server/bin
#ENV RSESSION_PROXY_RSTUDIO_1_4=True

RUN pip install uv
WORKDIR /tmp
COPY pyproject.toml ./
COPY marimo-server-proxy/ ./marimo-server-proxy/
RUN uv pip install --system -r pyproject.toml

# RStudio Server Install

RUN wget https://s3.amazonaws.com/rstudio-ide-build/server/jammy/${TARGETARCH}/rstudio-server-2024.09.2-399-${TARGETARCH}.deb \
    && gdebi -n rstudio-server-2024.09.2-399-${TARGETARCH}.deb \
    && rm rstudio-server-2024.09.2-399-${TARGETARCH}.deb \
    && echo server-user=${NB_USER} >> /etc/rstudio/rserver.conf

WORKDIR /home/${NB_USER}

USER ${NB_USER}
RUN jupyter server extension enable --py jupyter_server_proxy --sys-prefix
RUN jupyter server extension enable elyra

# Datashield R packages
RUN R -e "install.packages(c('DSI', 'DSOpal', 'dsBaseClient'), repos = 'https://cran.obiba.org', type = 'source')"
