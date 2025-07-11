FROM jupyter/scipy-notebook:latest


USER $NB_USER

RUN pip install marimo jupyter-server-proxy

COPY marimo_proxy.py /home/jovyan/marimo_proxy.py
COPY setup.py /home/jovyan/setup.py 

#COPY openrefine.py /home/jovyan/openrefine.py
#COPY setup2.py /home/jovyan/setup.py

WORKDIR /home/jovyan

RUN pip install .

RUN jupyter server extension enable --py jupyter_server_proxy --sys-prefix




