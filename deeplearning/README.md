# Deep Learning 
Deep Learning is just awesome! 

This README summerizes the journey I have been on for a few years and is servers as route map for myself.

# Data Prep

# Models and evaluations
## Regression type
```python
### Losses
loss_fn = nn.MSELoss() # Mean Square Error
# optimizer
optimizer = torch.optim.SGD(model1.parameters(), lr= .05)
```
### Evaluations
- Loss function
- Pearson correlationcoefficients
```python
correlation_coefficient = np.corrcoef(y.T, pred.T)[0,1]
```



## Classification type
