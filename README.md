# Multiphase-Production-Forecasting-Models

This repository is for educational purposes only. The script provides a flexible method to create **Multiphase Time Series Forecasting** models with multiple RNN variations. 
The contents of the scripts provided in this repository can be modified to achieve your own personal goals.

##
**Environment**
- **Warning:** The numpy, matplotlib, and pandas versions provided in the **"environments.ymla"** was necessary for successfully running this script without running into any errors/issues. Using different versions of these libraries may lead to errors when running this script.

- The provided scripts were tested with **Tensorflow 2.10 (Windows 11)**.
    - Tensorflow 2.10 is the latest version that supports training tensorflow models on a GPU instead of a CPU in Windows.
    - For variations of RNNs (LSTM, Bi-LSTM, etc.), if a GPU is available, it is highly recommended to use a GPU to train the models, as the CPU alternative may take much longer to train.
    - For additional speed during model training, I also recommend creating tensor datasets (as implemented in this project).
- This environment was created & managed inside **Anaconda** but, you can create virtual python environments or find other ways to recreate the same environment (**at your own risk**).  
- Before creating the environment, you may want to check your GPU type & download the matching  python, compiler, & CUDA versions.
    - https://www.tensorflow.org/install/source_windows (**For Windows Builds**)
![image](https://github.com/user-attachments/assets/70eedab5-bdee-4ba8-a7a5-8b3e73441a2c)
- You can use the provided the documents to rebuild the same (**working**) environment:
    - **"environments.ymla"**
    - **"Environment_Build.txt"** 

##
**Contents:**

##
**Data Pre-processing for Time Series based Forecasting (RNN variations):**
- **Many-to-Many** (fully available)
- **Many-to-One** (available as an example at the end of the script but, commented out for user's convenience - tested and confirmed to be working)
- **One-to-Many** (available but, requires slight modification to the script - change window generator settings)
- **One-to-One** (available but, requires slight modification to the script - change window generator settings)

##
**Deep Learning Models (RNN variations) & Machine Learning Models (ANN) for Simultanously Forecasting Multiphase (Oil/Gas/Water) Production Time Series:**
- **LSTM**
- **GRU**
- **Bi-directional LSTM**
- **Bi-directional GRU**
- **Deep-ANN** (Multi Layer Perceptron with a non-linear activation function)
- **Linear Regression** (with single layer ANN using a linear activation function)

##
**Additional Content:**
- Creation of Tensor datasets.
    - Allows faster training but, some information loss is possible - requires checking the model accuracy after training to ensure reasonable loss of accuracy vs. training speed gain.
- Different normalization methods for time series (z-score & min-max normalization)
    - In this case, the normalization was **instance based** and each producing well was normalized using its own individual statistics.
    - In this project, min-max normalization with a Dense sigmoid activation as the final layer of each model was used to predict the outcomes to avoid negative predictions after de-normalization (transforming the normalized predictions to its original scale).
    - In this case, the reason behind using instance based min-max normalization with a final Dense layer (using the sigmoid activation function) was because the behavior of producing wells (declining behavior) was predictable & the possible maximum and minimum values of production were known.
        - It was assumed that the maximmum value within an individual oil & gas well was already observed within 6 months of production and the mimimum possbile production was "~0".
        - The min-max normalization scheme transformed the target outputs within the 0-1 range and the sigmoid activation function was used to guess a the range of target outputs that lie between 0-1.
        - The same strategy may not work for problems in different domains and it is recommended to consider the problem domain when normalizing the dataset and creating the model.
- Training Tensorflow models (The models mentioned in the contents).
- Effective use of shut-in features.
    - **Days on production per month** feature was used to predict the future production.
    - In this case, these features could help the model accurately predict surges in production after long periods of shut-in (due to reservoir pressure build-up).
    - If additional features (e.g., pressure information) existed (it did not exist in our case), it is possbile to train a more accurate model.
    - Unfortunately, during my research, I found limited resources on creating more accurate forecasting models and none of them were useful in creating accurate multiphase production time series forecasts for oil & gas. It is highly recommended to use the domain knowledge (feature engineering) to build more accurate models for your own problem (if it is different than this problem).
- Capability to create models for long term forecasts.
    - Although this is an example of short term forecasts, it can be used as a base for creating models capable of accurate long term forecasts.
    - Accurate long term forecasts require models capable of accurately predicting long term dependencies (shameless self promotion here - but, a useful read to understand long term dependencies: https://library.seg.org/doi/abs/10.15530/urtec-2022-3721904).
    - Many RNNs, including gated RNNs can forget previous inputs during processing/training if the sequence is too long which may negatively impact model training (suboptimal training).
    - The gated version exist to help remember longer sequences (better than not having this option), however there are no guarantees that the model will remember the whole sequence especially if the sequence is long enough.
    - The datasets were created using a **window based training** where a window of fixed length of inputs are used to predict a window of fixed length outputs (in this case, a single value was used but, the script allows adjusting this value to multiple values). This option allows to the model to avoid running into the gradient vanishing problem (the main reason behind the forgetfullness of RNN based models) by shortening the sequences that the model uses to train and has to remember. The gated versions (LSTM, GRU, etc.) can help but, do not guarantee stable outcomes for each time series forecasting problem.
- Saving/ Loading the Tensorflow models.
- Displaying/Visualizing & Saving Plots of Multiphase Time Series Forecasts.
- Recognizing Loaded Models (recognizes the type of model by checking layer types, etc.).
- Creating & Modfiying Models.
    - A flexible function that allows creating desired layers, units,  model type (uni-directional vs. bi-directional), etc.
    - Additional benefits: convenient for users & necessary for running Optuna trials.
- Optimizing Models with Optuna using the "Flexible Function" (Tree Parzen Estimator - TPE).
- Saving/Loading Predictions/Results (as pickle).
- Creating custom loss functions (can be modified).
- Saving/Loading custom loss results (useful for checking/re-checking a previously trained model's performance without re-running model predictions).

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
