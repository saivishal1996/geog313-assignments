# Steps to run a container using Dockerfile

## To install miniconda
```
FROM continuumio/miniconda3:22.11.1
```

## copy environment.yml to create a conda env
```
COPY environment.yml .
RUN conda env create -f environment.yml 
```

This file includes all the packages that will be installed inside the env

## activate the conda env
```
RUN echo "conda activate a2-env" >> ~/.bashrc
ENV PATH="$PATH:/opt/conda/envs/a2-env/bin"
```


## to run jupyter lab
```
EXPOSE 8888
CMD ["jupyter", "lab", "--ip=0.0.0.0"]
```
