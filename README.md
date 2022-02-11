# Oil Price WTI Predict by LSTM and TCN model.
Predicting WTI index using LSTM 2021/06/31

# Summary
  Oil is a non-renewable energy source and plays an important role in economic development. In the issue of predicting oil prices, the ARIMA model in traditional econometric method can already make the model have good accuracy. However, using deep learning to process time series data have gradually emerged. Deep learning can avoids many of the limitations of traditional statistics. In addition, since we only care about the accuracy of the model, not the causal effect between variables, the use of deep learning to make predictions may perform better than tranditional regression models. This project will use deep learning methods TCN and LSTM for crude oil price(WTI) prediction.
  
  
# About TCN
  Temporal Convolution Network, TCN. Using CNN technology to process time series data. There are three kinds of volume base layers, the first is one-dimensional CNN, which is used to input data, the second is causal convolution, which can handle the sequence problem of time series, and the third is dilated convolution, which can slowly expand the convolution range, increasing the amount of data considered. In addition, CNN has the function of parallel operation, so the training speed is also faster than RNN.

# About LSTM
  The long-term and short-term memory model belongs to the recurrent neural network. The RNN LSTM model will consider the value of the previous input to weight the next input before outputting. The LSTM has memory nodes, which are responsible for memorizing or forgetting historical information, so it is suitable for time series data.
  
# Data
  From January 2014 to June 2021
  Data size : 1868
  
## Dependent variable
  West Texas Intermediate

## Independent variable
  1. West Texas Intermediate (sixty days ago)
  2. BRENT Index
  3. Crude oil inventories
  4. MSCI Energy ETF
  5. S&P500
  6. VIX Index

![image](https://user-images.githubusercontent.com/71583821/153644611-fc34555e-73dc-468a-9f2a-e9e655fbdfea.png)


# Model LSTM

## Hyper parameter
  
    look_back = 60 
    
    #-------for networks--------------#
    hidden_feature_dim = 32 
    hidden_layer_num = 2
    classes_num = 1
    dropout = 0.01
    bidirectional = False
    batch_first = True
    
    #-------for training--------------#
    learning_rate = 0.001
    epoch = 1000

## result
  *Validation RMSE Loss = 0.0492
  ![image](https://user-images.githubusercontent.com/71583821/153667271-561d25f2-d4c6-424b-8bd3-e2ad16929ffc.png)



# Model TCN 

## Hyper parameter
    #-------for networks--------------#
    look_back_windows = 5 
    kernel_size = 2
    dropout = 0.2

    #-------for training--------------#
    learning_rate = 0.001
    epoch = 1000

## result
  *Validation RMSE Loss = 0.0475
  ![image](https://user-images.githubusercontent.com/71583821/153667640-9d33e3ee-03ae-40f6-a413-4e7a45c6cf36.png)
  
  
