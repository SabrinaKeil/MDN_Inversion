# MDN Inversion
Machine learning (ML) approach for dispersion curve inversion using mixture density networks (MDN) based on Keil and Wassermann (2023).

The ML approach presented here allows the simultaneous estimation of layer numbers, layer depth and a complete probability distribution of the S-wave velocity structure. This is achieved by a two-step ML approach, where 1) a regular NN classifies the number of layers within the upper 100 m of the subsurface and 2) a mixture density network outputs the depth estimates together with a fully probabilistic solution of the S-wave velocity structure. We trained the model to distinguish structures with 2 - 7 subsurface layers.

The trained classification NN and the individual MDNs are located in the folder ./trained_models.   
With the jupyter notebook Prediction.ipynb the dispersion curve inversion can be performed using the already trained models.    
With the notebook Training-MDN.ipynb and Training-classification.ipynb the models can be trained on new data.   
The code for the set-up of the MDN is based on Earp et al. (2020).   

## Data preprocessing
Here are some requirements for the input data for the ML inversion, as well as for the training data:
1.) Love and Rayleigh Dispersion curves are used as input data together with their uncertainty vectors as seperate input 
2.) Dispersion curves and uncertainty vectors should be logarithmically resampled with 100 samples between 1 - 20 Hz corresponding to the frequency:  
#### freq=np.logspace(0,1.3,100,base=10)
3.) The output for the classification NN is the layer number as intiger value. The output for the MDNs are the layer depth as intiger value and the S-wave velocity.
4.) The phase velocity and uncertainty should be in km/s. The layer depth in m.



## References
Earp, S., Curtis, A., Zhang, X., & Hansteen, F. (2020). Probabilistic neural network tomography across Grane field (North Sea) from surface wave dispersion data. Geophysical Journal International, 223(3), 1741-1757.

Keil, S. and Wassermann, J. (2023). Dispersion curve inversion using mixture density networks. Geophysical Journal International.
