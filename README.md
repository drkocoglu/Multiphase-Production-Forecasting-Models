# Multiphase-Production-Forecasting-Models

This repository is for educational purposes only. The script provides a flexible method to create forecasting models with multiple RNN variations. 
The contents of the scripts provided in this repository can be modified to achieve your own personal goals.

##
**Environment**
- **Warning:** The numpy, matplotlib, and pandas versions provided in the **"environments.ymla"** was necessary for successfully running this script without running into any errors/issues. Using different versions of these libraries may lead to errors when running this script.

- The provided scripts were tested with **Tensorflow 2.10 (Windows 11)**.
    - This is the latest Tensorflow version that supports training tensorflow models & predicting with the trained models on GPU in Windows.
- This environment was created & managed inside Anaconda but, you can create virtual python environments or find other ways to recreate the same environment (at your own risk).  
- Before creating the environment, you may want to check your GPU type & download the matching  python, compiler, & CUDA versions.
    - https://www.tensorflow.org/install/source_windows (For Windows Builds)
![image](https://github.com/user-attachments/assets/70eedab5-bdee-4ba8-a7a5-8b3e73441a2c)
- You can use the provided the documents to rebuild the same (working) environment:
    - **"environments.ymla"**
    - **"Environment_Build.txt"** 

##
**Contents:**

##
**Data Pre-processing for Time Series based Forecasting (RNN variations):**
- Many-to-Many (fully available)
- Many-to-One (available as an example at the end of the script)
- One-to-Many (available but, requires slight modification to the script - change window generator settings)
- One-to-One (available but, requires slight modification to the script - change window generator settings)

##
**Deep Learning Models (RNN variations & ANN) for Forecasting Multiphase (Oil/Gas/Water) Production Time Series:**
- LSTM
- GRU
- Bi-directional LSTM
- Bi-directional GRU
- ANN (Multi Layer Perceptron)

##
**Additional Content:**
- Training tensorflow models (The RNN variations previously mentioned)
- Saving/ Loading the tensorflow models
- Displaying/Visualizing & Saving Plots of Multiphase Time Series Forecasts
- Recognizing Loaded Models
- Creating & Modfiying Models
    - A Flexible Function that allows creating user desired layers, units,  model type (uni-directional vs. bi-directional), etc.
- Optimizing Models with Optuna using the "Flexible Function" (Tree Parzen Estimator - TPE)
- Saving/Loading Predictions/Results (pickles)
- Creating Custom Loss Functions
- Saving/Loading Custom Loss Results

##
**Citation:**

If this repository contributed to your work please consider citing the associated paper:

##
    
    @article{KOCOGLU2024212688,
      title = {Improving the accuracy of short-term multiphase production forecasts in unconventional tight oil reservoirs using contextual Bi-directional long short-term memory},
      journal = {Geoenergy Science and Engineering},
      volume = {235},
      pages = {212688},
      year = {2024},
      issn = {2949-8910},
      doi = {https://doi.org/10.1016/j.geoen.2024.212688},
      url = {https://www.sciencedirect.com/science/article/abs/pii/S2949891024000587},
      author = {Yildirim Kocoglu and Sheldon B. Gorell and Hossein Emadi and Dorcas S. Eyinla and Farshad Bolouri and Yavuz C. Kocoglu and Aman Arora}    
    }
