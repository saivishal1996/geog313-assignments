FROM continuumio/miniconda3:22.11.1

COPY environment.yml .
# create a conda env
RUN conda env create -f environment.yml   

# Activate the conda environment
RUN echo "conda activate a2-env" >> ~/.bashrc
ENV PATH="$PATH:/opt/conda/envs/a2-env/bin"

# Create a non-root user and switch to that user
RUN useradd -m jupyter
USER jupyter

WORKDIR /home/jupyter/assignment

# Expose the JupyterLab port
EXPOSE 8888

# Start JupyterLab
CMD ["jupyter", "lab", "--ip=0.0.0.0"]
