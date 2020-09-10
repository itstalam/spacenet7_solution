# spacenet7_solution

motokimura's solution to SpaceNet7 challenge

## Instructions for Model Development

This section provides instructions for the model development phase.

### Download SpaceNet7 data

```
# prepare data directory
DATA_DIR=${HOME}/data/spacenet7/spacenet7
mkdir -p ${DATA_DIR}
cd ${DATA_DIR}

# download and extract train data
aws s3 cp s3://spacenet-dataset/spacenet/SN7_buildings/tarballs/SN7_buildings_train.tar.gz .
tar -xvf SN7_buildings_train.tar.gz

# download and extract test data
aws s3 cp s3://spacenet-dataset/spacenet/SN7_buildings/tarballs/SN7_buildings_test_public.tar.gz .
tar -xvf SN7_buildings_test_public.tar.gz
```

### Prepare training environment

```
# git clone source
PROJ_DIR=${HOME}/spacenet7_solution
git clone git@github.com:motokimura/spacenet7_solution.git ${PROJ_DIR}

# build docker image
cd ${PROJ_DIR}
./docker/build.sh

# launch docker container
ENV=desktop1
./docker/run.sh ${ENV}
