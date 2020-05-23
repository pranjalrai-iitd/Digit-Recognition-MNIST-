# Digit Recognition (MNIST)
99.5 % accuracy on MNIST dataset!

## CNN

### Notation

```
32C3s1 = convolution layer with 32 filters of size (3,3) with stride of 1, Same padding and relu activation
M2s2 = maxpooling layer with filter of size (2,2) ans stride of 2
D10softmax = dense layer with 10 units and softmax activation
```

### Network

```
32C3s1 

  BatchNormalization 
  
    32C5s1 
    
      M2s2 
      
        Dropout(0.5) 
        
          32C3s1
          
            BatchNormalization
            
              32C5s1 
              
                M2s2 
                
                  Dropout(0.5)
                  
                    Flatten
                    
                      D128relu
                      
                        Dropout(0.5)
                        
                          D10softmax
```              
 ### Optimizer
 
 Adam with learning rate of 0.001. 
 
 Learning rate is annealed by a factor of 0.2 with patience of 3 epochs.
 
 
