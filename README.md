# DCASE2019 task4 baseline: Sound event detection in domestic environments

You can find discussion about the dcase challenge here: [dcase_discussions](https://groups.google.com/forum/#!forum/dcase-discussions).
Challenge [website](http://dcase.community/challenge2019/)

## Dependencies

Python >= 3.6, pytorch >= 1.0, cudatoolkit=9.0, pandas >= 0.24.1, scipy >= 1.2.1, pysoundfile >= 0.10.2,
librosa >= 0.6.3, youtube-dl >= 2019.1, tqdm >= 4.31.1, ffmpeg >= 4.1, dcase_util >= 0.2.5, sed-eval >= 0.2.1

A simplified installation procedure example is provide below for python 3.6 based Anconda distribution for Linux based system:
1. [install Ananconda](https://www.anaconda.com/download/)
2. launch conda_create_environment.sh`

**Note:** `The baseline has been tested with python 3.6, on linux (CentOS 7)`

## Dataset
**The dataset is composed of two subset that can be downloaded independently:**

1. (Real recordings) launch `python download_data.py` (in `baseline/` folder)
2. (Synthetic clips) download at : [synthetic_dataset](https://doi.org/10.5281/zenodo.2583796)

You should have a development set structured in the following manner:

```
dataset root
└───metadata			              (directories containing the annotations files)
│   │
│   └───train			              (annotations for the training sets)
│   │     weak.csv                    (weakly labeled training set list and annotations)
│   │     unlabel_in_domain.csv       (unlabeled in domain training set list)
│   │     synthetic.csv               (synthetic data training set list and annotations)
│   │
│   └───validation			          (annotations for the test set)
│         validation.csv                (validation set list with strong labels)
│         test_2018.csv                  (test set list with strong labels - DCASE 2018)
│         eval_2018.csv                (eval set list with strong labels - DCASE 2018)
│    
└───audio					          (directories where the audio files will be downloaded)
    └───train			              (audio files for the training sets)
    │   └───weak                      (weakly labeled training set)
    │   └───unlabel_in_domain         (unlabeled in domain training set)
    │   └───synthetic                 (synthetic data training set)
    │
    └───validation			          (validation set)       
```


# Description

This task is the follow-up to [DCASE 2018 task 4](../challenge2018/task-large-scale-weakly-labeled-semi-supervised-sound-event-detection). 
The task evaluates systems for the large-scale detection of sound events using weakly labeled data (without timestamps). 
The target of the systems is to provide **not only the event class but also the event time boundaries** given that multiple events can be present in an audio recording. 
The challenge of exploring the possibility to **exploit a large amount of unbalanced and unlabeled training data** together with a small weakly annotated training set to improve system performance remains but an **additional training set with strongly annotated synthetic data** is provided. 
**The labels in all the annotated subsets are verified and can be considered as reliable.**  An additional scientific question this task is aiming to investigate is whether we really need real but partially and weakly annotated data or is using synthetic data sufficient? or do we need both?

Further information on [dcase_website](http://dcase.community/challenge2019/task-sound-event-detection-in-domestic-environments)

## Authors

Nicolas Turpault, Romain Serizel, Justin Salamon, Ankit Parag Shah, 2019 -- Present
