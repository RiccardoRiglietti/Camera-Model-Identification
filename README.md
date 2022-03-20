# Camera Model Identification

Detecting the camera model used to shoot a picture enables to solve a wide series of forensic problems, from copyright infringement to ownership attribution [1].

This project aims to replicate and then improve on the results of the paper "First Steps Toward Camera Model Identification
with Convolutional Neural Networks", by identifying the camera model of the images with a CNN feature extraction followed by a classification using an ensamble of SVMs.

The dataset used is: https://faui1-files.cs.fau.de/public/mmsec/datasets/fodb/ containing 3861 images, consisting in 143 scenes each photographed from the same location with 27 smartphones.  

## Improvement

We obtained better results on our dataset with an approach simpler than the one described in the paper by finetuning the Efficient-Net architecture (EfficientNetB1 from the built-in neural nets of Tensorflow). Given the small size of our dataset we used dropout and early stopping to avoid overfitting.

## Results

Validation accuracy:

- "BondiNet": 30.4%
- "BondiNet" + OneVsRest SVM: 35.1%
- "BondiNet" + OneVsRest SVM: 67.9%
- EfficientNetB1 finetuned: 67.9 %

The confusion matrices of the various approaches can be seen in the notebooks.

## Authors

Riccardo Riglietti, Yannick Moell, Ascanio Santomarco

## Bibliography

[1] https://arxiv.org/pdf/1603.01068.pdf
