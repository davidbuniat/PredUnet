# PredUnet
Predict next frame using RSUnet architecture. Implemented using Cavelab framework.
For model and training parameters refer to `hparams.json`.

## Install
To run in Cavelab environment where all dependancies are installed, you need to have nvidia-docker installed.
```
nvidia-docker run -it --net=host \
      -v PATH_TO_CRACK_FOLD_DETECTOR_REPO:/PredUnet \
      davidbuniat/cavelab:latest-gpu bash
```
Then
```
cd /PredUnet
```

## Data
You need to preprocess your own data sampled from big array, represented by CloudVolume object, in `src/process_data.py`. It will create TFRecords files `/data` folder. All parameters are defined in `hparams.json`

```
python src/process_data.py
```

Once the data is ready. To train the model use the following script
```
python src/model.py
```


##  Logs
Logs including model checkpoints will be stored in `logs` data.


## Status
Still in development. The model is not working, but the repository is a use case for [Cavelab](https://github.com/Loqsh/cavelab).
