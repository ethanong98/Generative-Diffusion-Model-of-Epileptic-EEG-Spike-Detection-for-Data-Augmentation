# Generative Diffusion Model of Epileptic EEG Spike Detection for Data Augmentation
<img src="Image/sample_EEG.png" width=500px>

* This repository consist of code for implementation in "Generative Diffusion Model of Epileptic EEG Spike Detection for Data Augmentation"

## Abstract
Epilepsy diagnosis relies significantly on Electroencephalogram (EEG) analysis, particularly the detection of interictal epileptiform discharges (IEDs), such as spikes. Manual identification of these discharges is time-intensive. Despite existing automated methods, clinical adoption remains limited due to suboptimal performance by the classifiers built for detecting the spike. This study utilizes the classifier-free guidance diffusion model for data augmentation using WaveGrad architecture by training on multi-electrode EEG data. Besides, this study proposes a preprocessing technique to enhance the model’s focus while retaining the most useful information. Results show that the deep learning classifiers’ performance is increased after training on the data synthesized by the diffusion model. 

## Working directories

```
   |---0_EDF_file_analysis.ipynb
   |---0_Pre-process_EDF_FILE.ipynb
   |---1_Visualize_EEG_Signal.ipynb
   |---2_Training_Diffusion_Model.ipynb
   |---3_Training_Classifiers.ipynb
   |---3_Training_Diffusion_Classifiers.ipynb
   |---4_Evaluate_Diffusion_Model.ipynb
   |---5_Training_Classifiers_with_synthesized_data.ipynb
   |---6_Label_EEG_data.ipynb

   |---model.py    # Contain the Neural Network implementation in pytorch
   |---settings.py # All the settings
   |---utility.py  # Utility function
   
   |---EEG_Dataset
       |---patientID_1
           |--- patientID_1.edf
       |---patientID_2
           |--- patientID_2.edf
       ...
       |---patientID_n
           |--- patientID_n.edf
   |---EEG_csv
       |---eeg1.csv
       |---eeg2.csv
       ...
       |---eeg40.csv
       |---annotation.json
```

## Way to run the code
1. Install all the dependency library in your python environment. 

    ```pip install -r requirements.txt```
> *Make sure you have pytorch installed in your environment, if no, you can refer to [Pytorch Website](https://pytorch.org/get-started/locally/)* 

2. Place your EEG data in '.edf' format into the 'EEG_dataset' directory

3. Analyze your EEG data using 0_EDF_file_analysis.ipynb

4. Adjust the settings in 'settings.py' based on your EEG data's properties

5. Preprocess the EDF file into csv file, the EEG_csv folder is auto generated

6. Visualize your EEG data before and after preprocess. Repeat from step 4 if the visualization does not meet your expectation

7. Train and evaluate the diffusion model and classifiers by consequently running the jupyter notebook file '2_Training_Diffusion_Model.ipynb', '3_Training_Classifiers.ipynb', ...
