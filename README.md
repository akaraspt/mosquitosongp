# MosquitoSong+: A noise-robust deep learning model for mosquito classification from wingbeat sounds

A deep learning model for mosquito species and sex classification based on a low-sample-rate raw audio signal.

## Setup Environment
```bash
conda create -n mosquito python=3.7
conda activate mosquito
pip install --upgrade pip
pip install numpy pandas matplotlib seaborn imblearn soundfile librosa jupyterlab
conda install -c conda-forge cudatoolkit=11.0 cudnn=8.0
mkdir -p $CONDA_PREFIX/etc/conda/activate.d
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/' > $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
pip install tensorflow==2.4.0
```

## How to run
To test the model performance. You can easily do it by following these steps.
1.	Download the mosquito and environmental noise recordings from this link (TBD). 
1.	Place mosquito recordings to `./data/mosquito_recordings/`. 
1.	Place environmental noise recordings to `./data/environmental_noise_recordings/`. 
1.	Download the classification models from this [link](https://drive.google.com/drive/folders/1TfLHtHpVAfus6msjiDjgdeQHT9m3gnX7?usp=sharing).
1.	Place classification models to `models` folder.
1.	Run all cells for `predictions.ipynb`. 
After the jupyter notebook file finished, the classification results will be generated as .xlsx file in `classification_results` folder. The results include per-class and average precision, recall, and F1-score. There are result from each round of 10-fold end as _raw file and average result end as _avg.


## Citation
TBD

## Licence

* For academic and non-commercial use only
* Apache License 2.0