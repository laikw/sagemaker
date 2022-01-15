# FROM tensorflow/tensorflow:2.3.0
FROM nvcr.io/nvidia/tensorflow:21.12-tf2-py3
RUN apt-get update 
RUN apt-get install -y git
RUN pip install --upgrade pip
RUN pip install ipykernel && \
    python -m ipykernel install --sys-prefix && \
    pip install --upgrade --quiet --no-cache-dir \
    boto3 sagemaker matplotlib 

# Copies the training code inside the container
COPY train.py /opt/ml/code/train.py

# Defines train.py as script entrypoint
ENV SAGEMAKER_PROGRAM python train.py