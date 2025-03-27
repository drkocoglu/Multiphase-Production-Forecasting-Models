# Multiphase-Production-Forecasting-Models

This repository is for educational purposes only. The script provides a flexible method to createThe contents (scripts, etc.) provided in this repository can be modified to achieve your personal tasks.

##
**Contents:** 
** Data Pre-processing for Time Series based Forecasting (RNN variations):**
- Many-to-Many (fully available)
- Many-to-One (available as an example at the end of the script)
- One-to-Many (available but, requires slight modification to the script - change window generator settings)
- One-to-One (available but, requires slight modification to the script - change window generator settings)

** Deep Learning Models (RNN variations & ANN) for Forecasting Multiphase (Oil/Gas/Water) Production Time Series:**
- LSTM
- GRU
- Bi-directional LSTM
- Bi-directional GRU
- ANN (Multi Layer Perceptron)

** What else is availabe?:**
- Training tensorflow models (The RNN variations mentioned above)
- Saving/ Loading tensorflow models
- Displaying/Visualizing & Saving Plots of Multiphase Time Series Forecasts
- Recognizing Loaded Models
- Creating & Modfiying Models (Flexible Function - allows creating desired layers, type (uni-directional or bi-directional), units, etc. with simple user prompts)
- Optimizing Models with Optuna using the Flexible Model Creation Function (Tree Parzen Estimator - TPE)
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
