# Detecting brain seizures from EEG signals through Deep Learning (Kaggle Competition)

Competition: https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification

**Background:** Across the globe, individuals suffer from traumatic brain injuries, epilepsy, and other forms of brain damage. This reality prompts an important question: 
how are medical professionals tackling these issues to provide solutions for those affected?

Enter the transformative power of EEG technology. By measuring the brain's voltage signals, clinicians can detect patterns indicative of irregular brain activity at an early stage, 
paving the way for timely treatment. However, this innovative approach is not without its challenges. Firstly, EEG signals are inherently complex and exhibit significant variability, necessitating the expertise of highly qualified professionals for accurate interpretation—a resource that is often scarce. 
Furthermore, the detection of subtle anomalies, which is crucial for a definitive diagnosis, remains a formidable task. Coupled with the sheer volume of data that requires analysis, the process is not only time-consuming but also fraught with difficulties.


**Objective:** The goal is to develop a transformative model to detect seizures from EEG signals, that could unlock the transformative benefits for neurocritical care, epilepsy, and drug development.

**Data:** We are provided with 15k+ EEG files and 10k+ EEG Spectrogram files. Each file has a 50 second long recording of EEG signals, and is being divided into different segments for
each patient. The main section to look at is the middle 10 seconds recording for each segment. There are 6 patterns of interest: 
1. Seizure (SZ)
2. Generalized Periodic Discharges (GPD)
3. Lateralized Periodic Discharges (LPD)
4. Generalized Rhythmic Delta Activity (GRDA)
5. Lateralized Rhythmic Delta Activity (LRDA)
6. “Other” - brain pattern that doesn’t fit into the above categories
~46% of rows have “other” votes

The patterns are labelled based on expert annotators "votes": 
1. Edge cases - votes evenly split between 2 patterns
2. Proto pattern - Edge case involving “other” pattern
3. Vote count - Total vote count is not always same

**Feature Engineering:** The EEG Signal was processed and features were extracted using the following techniques:  
1. Denoising signals: Wavelet transform ('db8')
<p align="center">
  <img src="https://github.com/user-attachments/assets/124c4125-3154-41f0-8ebf-eb812809edc6" alt="F3_raw" width="400"/>
  <img src="https://github.com/user-attachments/assets/d9c8224d-76f8-430b-a8ed-80192ad05142" alt="F3_processed" width="400"/>
</p>


2. Welch
3. Discrete Wavelet transform
4. Extracted statistics: Log sum, mean average power, standard deviation
5. Shannon Entropy


**Deep Learning:** CNN-LSTM architecture, based on this paper

Hezam Albaqami, Ghulam Mubashar Hassan, Amitava Datta,
MP-SeizNet: A multi-path CNN Bi-LSTM Network for seizure-type classification using EEG,
Biomedical Signal Processing and Control,
Volume 84,
2023,
104780,
ISSN 1746-8094,
https://doi.org/10.1016/j.bspc.2023.104780.





