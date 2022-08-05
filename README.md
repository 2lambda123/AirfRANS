# AirfRANS
In this repository, you will find the different python scripts to train the available models on the AirfRANS dataset proposed at the NeurIPS 2022 Datasets and Benchmarks Track conference. You can find the paper submission [here](https://openreview.net/forum?id=Zp8YmiQ_bDC&referrer=%5Bthe%20profile%20of%20Florent%20Bonnet%5D(%2Fprofile%3Fid%3D~Florent_Bonnet1)).

## Requirements
* Python 3.9.12
* PyTorch 1.11.0 with CUDA 11.3
* PyTorch Geometric 2.0.4
* PyVista 0.36.1
* Seaborn 0.11.2

## Training
To train a model, run main.py with the desired model architecture:

```
python main.py GraphSAGE -t full
```

Note that you must have the dataset in folder ```Dataset/``` at the root of this repository, you can download the dataset [here](https://data.isir.upmc.fr/extrality/NeurIPS_2022/Dataset.zip). You can change the parameters of the models and the training in the ```params.yaml``` file.

## Usage
```usage: main.py [-h] [-n NMODEL] [-w WEIGHT] [-t TASK] [-s SCORE] model

positional arguments:
  model                 The model you want to train, choose between MLP, GraphSAGE, PointNet, GUNet

optional arguments:
  -h, --help            show this help message and exit
  -n NMODEL, --nmodel NMODEL
                        Number of trained models for standard deviation estimation (default: 1)
  -w WEIGHT, --weight WEIGHT
                        Weight in front of the surface loss (default: 1)
  -t TASK, --task TASK  Task to train on. Choose between "full", "scarce", "reynolds" and "aoa"
                        (default: full)
  -s SCORE, --score SCORE
                        If you want to compute the score of the models on the associated test set.
                        (default: 0)
```
 
 ## Results
After training a model, the different training plots and training logs will be at the root of the ```metrics``` folder. The scores of the trained model on the associated test set are written in the folder ```scores/TASK/```. The visualization of the force coefficients plot and the boundary layers can be generated via the notebook ```visualization.ipynb```. You can find the scores and the plots given in the paper [here](). The dataset statistics can also be generated via the notebook ```dataset_stats.ipynb```.
