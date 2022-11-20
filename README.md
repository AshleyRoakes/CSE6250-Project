# CSE6250-Project

How to run this project

Can be run with docker or local but prefer to be running with anaconda to use GPU

# Clone the Project

```
git clone https://github.com/AshleyRoakes/CSE6250-Project.git
cd CSE6250-Project
```

# Get the data
Access is needed to retrieve the MIMICIII data

```
cd data
mkdir mimic-iii-clinical-database-1.4
cd ..
```

Download and add the following files to the created mimic-iii-clinical-database-1.4 folder


- D_ICD_DIAGNOSES.csv.gz
- D_ICD_PROCEDURES.csv.gz
- DIAGNOSES_ICD.csv.gz
- NOTEEVENTS.csv.gz
- PROCEDURES_ICD.csv.gz


# DOCKER

```
docker run -it --name project -p 8888:8888 -v <path to the project dir>:/mnt/host continuumio/anaconda3:latest bash

cd /mnt/host/

conda create -y --name py38 python=3.8.8

conda activate py38

conda install pip

conda install gensim  # install with conda for fast word2vec

pip install -r requirements.txt #remove gensim from here if using docker anaconda for faster results

jupyter notebook --ip=0.0.0.0 --port=8888 --allow-root

```

Follow the link in the docker cli window on your local web browser to run all jupiter sections

The same steps can be followed locally