### Motivation:
Can we emulate an ocean state estimate model just using MITgcm outputs using UNet? This is pertinent to my thesis; if we can emulate MITgcm using machine learning, can run high resolution features over a long period in a much more computationally efficient and feasible way. This will allow experimentation of estimating ocean states in any high resolution/computationally expensive scenario. 

### Data:
I will be using MITgcm snapshot outputs. To start, I will be just using 2D wind velocity data alone as input. This data will be in the form of 2D arrays of wind velocity at different time steps. The dataset is dependent upon snapshot intervals and total model run, but with the grid size of the model being fairly, it will be easy to process. Each snapshot is 62 x 62, each point signifying magnitude and direction of the velocity. 

### Model:
I will be using a UNet architecture for emulating the ocean states using MITgcm data as input. This is appropriate because CNNs, and UNet in particular, has been shown in various papers to be effective in emulating the ocean state using MITgcm data. I will be using mean squared error as the loss function to evaluate the model against the MITgcm snapshots at particular time steps. 

### Analysis: 
I will look at RMSE of certain timesteps of the model predictions against the MITgcm snapshots. The results will tell me how close the model is able to emulate the ocean state compared to MITgcm over time. As a baseline I can also compare if my model is doing better than just the intial condtions assuming no change. 
