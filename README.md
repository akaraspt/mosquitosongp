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
1.	Download the mosquito and environmental noise recordings from this [link](https://drive.google.com/drive/folders/1jvRfJ4X3UKtyV8regcHRgZLuzwPQWW6N?usp=sharing). 
1.	Place mosquito recordings to `./data/mosquito_recordings`. 
1.	Place environmental noise recordings to `./data/environmental_noise_recordings`. 
1.	Download the classification models from this [link](https://drive.google.com/drive/folders/1TfLHtHpVAfus6msjiDjgdeQHT9m3gnX7?usp=sharing).
1.	Place classification models to `./models` folder.
1.	Run all cells for `predictions.ipynb`. 

After the jupyter notebook file finished, the classification results will be generated as .xlsx file in `classification_results` folder. The results include per-class and average precision, recall, and F1-score. There are result from each round of 10-fold end as _raw file and average result end as _avg.

## Tiny MosquitoSong Dataset
The mosquito wingbeat sounds were collected from the laboratory of the Medical Entomology Department of the Faculty of Tropical Medicine at Mahidol University. The research has been approved for the animals involving research by the Institutional Review Board of the Faculty of Tropical Medicine, Mahidol University (FTM-ACUC 030/2020). The recordings consist of four mosquito species: Aedes aegypti, Aedes albopictus, Anopheles dirus, and Culex quinquefasciatus from both males (M) and females (F). Samples mosquitoes were from laboratory strains raised in the Medical Entomology Department of the Faculty of Tropical Medicine. They were individually put into a small cylindrical net cage (8cm in width and 12cm in height). A condenser microphone (Studio Behringer ECM8000 measurement) and a low-cost (Primo EM172) microphone with 24-bit depth and 96 kHz sampling rate was used to record the wingbeat sounds.

The raw recordings were processed by extracting only the periods containing wingbeat sounds. These wingbeat sounds were then split into the $300$-ms epochs with $150$-ms overlap for training and evaluating the classification model. Environmental noises were recorded from vehicles, animals (cats and dogs), and human activity (watering with a garden hose, sweeping, and cutting grass). These noises were recorded using two microphones in an urban environment to represent a realistic mixture of different noises.  As we would like to develop an approach that could eventually be deployed in conjunction with mosquito traps, there will also be noise from the fans of the traps that pull in the mosquitoes flying nearby. Thus we also collected the fan noises from the Centers for Disease Control and Prevention (CDC) - a light trap model 512  (John W. Hock, Gainesville, FL) and a miniature light trap Model 2836BQ  (BioQuip, Rancho Dominguez, CA). The two condenser microphones were set with a 30-cm distance between them.

Content

* 1324 wingbeat recordings correctly labeled with mosquitoes species and sex
* 4 mosquito species (Ae. aegypti, Ae. albopictus, An. dirus, Cu. quinquefasciatus)
* 3 genera of mosquito species (Aedes, Anopheles, Culex)
* 8 environment noise recordings
* 4 lighttraps fan noise recordings


## Citation
TBD

## Licence

* For academic and non-commercial use only
* Apache License 2.0