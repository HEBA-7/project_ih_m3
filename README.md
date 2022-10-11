# Project module-3

The objective of this project is to have a model for predicting the diamonds prices having the minimum error possible.

### Workflow

The process used during the project was the folowing:

    1. Concat the diferent datasets (color, clarity, etc...)
    
    2. EDA:
        a). If there are nulls and types of variables.
        b). Analyzing the diferent variables and the correlation between the principal one ("price").
        c). Identifying the usless values:
            df.query("x==0 or y==0 or z==0")
        d). Identifying the outliers:
            df.drop(df.query("z>10 or y>10").index, inplace=True)
            df.query("x==0 or y==0 or z==0")
            
     3. Convert the categorical variables to numeric.
        a). Here is important to replace the categorical value to number, ordering the puntuation for every category. For example:          df.clarity.replace({"SI2":8, "SI1":7, "VS1":6, "VS2":5, "VVS2":4, "VVS1":3, "I1":1, "IF":2}
        
     4. Convert the objects types to int or float.
     
     5. Choose the best variables.
     
     6. Training the model.
     
     7. Metrics for choosing the best model calculating the rmse:
         a.) linear_model.Lasso()
         b). ElasticNet()
         c). Ridge()
         d). SVR()
         e). SGDRegressor()
         f). LinearRegression()
         g). GradientBoostingRegressor
         h). RandomForestRegressor
         
     8. Testing the model.
      
### Best Model

The best model is RandomForestRegressor with the next hyperparameters:

- (n_estimators = 1000, random_state=123, max_depth = 32)

### Analysis

For choosing the best model, was used the next tools:

- RMSE= the metric for choosing the best model.
- cross_val_score: simulating the possible error for all the predicives prices.
- grid_search.fit(X,y): was used to find the optimals hiperparameters.
                       




