# Time Series Identification

## Requirements
Python version: 3.6.2
Python Package: h5py, nltk 3.2.4, anaforatools, keras 2.2.0


## Usages

* `preprocess.py` - Extract features from documents and generate the model input files and annofora annotations
* `model_training.py` - Train a time entity identification models.
* `data/testing` - Testing data.
* `data/training` - Training data.
* `images` - Plot for testing data.


To processe the documents, please run - Step1 - Preprocessing un-annotated files:
This will generate processing files in data/po folder
```
python preprocess.py -raw data/training -xml data/annotationXml -processed_output data/po -model_output data/model
```

To train a time entity identification model - Step2 - Model Training:
This will train the model and save the model data/model/trainedModel/model/model_result.hdf5
```
python model_training.py -input data/model -output data/model/trainedModel -raw data/training -processed_path data/po -input data/model -out data/output
```
To test a time entity identification model - Step3:
This will load the trained model and generate the graph with recall, precession and F1 score
```
python model_training.py -input data/model -output data/model/trainedModel -raw data/training -processed_path data/po -input data/model -out data/output -testing True
```
