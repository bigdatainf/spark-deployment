FROM ghcr.io/bigdatainf/spark-base:0.0.1

# -- Layer: JupyterLab

ARG spark_version=3.4.0
ARG jupyterlab_version=3.4.8

RUN apt-get update -y && \
    apt-get install -y python3-pip && \
	pip3 install pypandoc==1.5 && \
    pip3 install pyspark==${spark_version} jupyterlab==${jupyterlab_version} && \
	pip3 install graphframes && \
    rm -rf /var/lib/apt/lists/* && \
    ln -s /usr/local/bin/python3 /usr/bin/python

# -- Runtime

EXPOSE 8888
WORKDIR ${SHARED_WORKSPACE}
CMD jupyter lab --ip=0.0.0.0 --port=8888 --no-browser --allow-root --NotebookApp.token=

