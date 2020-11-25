# timeident

## Requirements
Python version: 3.6.2
Python Package: h5py, nltk 3.2.4, anaforatools, keras 2.2.0 , theano 1.0.2,regex 2.4.144


## Usages

* `preprocess.py` - Extract features from documents and generate the model input files and annofora annotations
* `model_training.py` - Train a time entity identification models.


To processe the documents, please run - Step1:
```
python preprocess.py -raw data/training -xml data/annotationXml -processed_output data/po -model_output data/model
```

To train a time entity identification model - Step2:
```
python model_training.py -input data/model -output data/model/trainedModel -raw data/training -processed_path data/po -input data/model -out data/output
```

