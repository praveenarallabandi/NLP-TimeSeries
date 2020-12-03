# Time Series Identification

## Requirements
* Python version: 3.6.2
* Python Package: h5py, nltk 3.2.4, anaforatools, keras 2.2.0, numpy, matplotlib
* Dependencies - [INSTALL](https://github.com/praveenarallabandi/NLP-TimeSeries/blob/main/INSTALL)

## Usages

* `preprocess.py` - Extract features from documents and generate the model input files and annofora annotations
* `model_training.py` - Train a time entity identification models.
* `data/testing` - Unannotated Testing data.
* `data/training` - Unannotated Training data.
* `images` - Plot for testing data.


**Step1** - Run the below command for Preprocessing
* Will prompt NTLK downloader, select all and all-corpa
* This will generate processing files in data/po folder
```
python preprocess.py -raw data/training -xml data/annotationXml -processed_output data/po -model_output data/model
```

**Step2** - Run the below command to train the RNN model
* This will train the model and save the model data/model/trainedModel/model/model_result.hdf5
* epoch size is set to 5 in model_training.py file
* Note - If prompted for NLTK please ignore it by closing the prompt
```
python model_training.py -input data/model -output data/model/trainedModel -raw data/training -processed_path data/po -input data/model -out data/output
```

**Step3** - Run the below command to test the model
* This will load the trained model and generate the graph with recall, precession and F1 score
```
python model_training.py -input data/model -output data/model/trainedModel -raw data/training -processed_path data/po -input data/model -out data/output -testing True
```
