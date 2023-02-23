# MDN_Inversion
Machine learning (ML) approach for dispersion curve inversion using mixture density networks (MDN) based on Keil and Wassermann (2023).

The ML approach presented allows the simultaneous estimation of layer numbers, layer depth and a complete probability distribution of the S-wave velocity structure. This is achieved by a two-step ML approach, where 1) a regular NN classifies the number of layers within the upper 100 m of the subsurface and 2) a mixture density network outputs the depth estimates together with a fully probabilistic solution of the S-wave velocity structure. We trained the model to dintignuish structures with 2 - 7 subsurface layers.

The trained classification NN and the individual MDNs are located in the folder ./trained_networks.
With the jupyter notebook Prediction.ipynb the dispersion curve inversion can be performed using the already trained models.
With the notebook .ipynb and .ipynb the models can be trained on new data.


## Data preprocessing
Here are some requirements for the input data for the ML inversion, as well as for the training data:




## References
Earp, S., Curtis, A., Zhang, X., & Hansteen, F. (2020). Probabilistic neural network tomography across Grane field (North Sea) from surface wave dispersion data. Geophysical Journal International, 223(3), 1741-1757.

Keil, S. and Wassermann, J. (2023). Dispersion curve inversion using mixture density networks. Geophysical Journal International.
