# DA24M029-DA6401-Assignment2

Make sure you download the inaturalist dataset and keep it in the same directory as these files and provide its path in the notebooks as required. 

# File Organization

```
DA24M029-DA6401-Assignment2/
│
├── best_models/            # some best/saved models present 
├── wandb/                  # cache for wandb
├── partA.ipynb             # notebook relevant to partA
├── partB.ipynb             # notebook relevant to partB
├── README.md               # this readme file
```


Just simply run `partA.ipynb` (or `partB.ipynb`) for the relevant task A or B cell by cell starting from the top. All the libraries will be installed as required. 

For Part A,
Run upto `Sweep Config and Run` cell, for sweep train task. You may change parameters as necessary. Run cells after it for best model tasks, training (if model not saved; or you may delete the saved models from `best_models` folder for a fresh model train with best configs, as long as you know them). 
Best Model:  Final Test Accuracy: 0.3790 (Check it in notebook before running the notebook)
```
best_config = {
    "num_filters": [8, 16, 32, 64, 128],     # Filter sizes in each conv layer
    "kernel_size": 3,                           # Convolution kernel size
    "activation": "silu",                       # Activation function
    "use_batchnorm": True,                      # BatchNorm after conv?
    "dropout": 0.3,                             # Dropout rate
    "dense_neurons": 256,                       # FC layer size before classifier
    "num_classes": 10,                        # Number of output classes
    "lr": 0.00107,                                 # Learning rate
    "batch_size": 64,                           # Just for tracking, if dynamic
    "augment": False,                            # If data augmentation is used
    "epochs": 10                                # Number of training epochs
}
```
For Part B, 
Run upto finetune runner md cell, with config changeable by us in `run_finetune_training` function parameters while its execution, for finetuning, and run cells thereafter for test accuracy. 
For inception model only, if you want to run, comment and uncomment the code lines as per the required instructions, in `train one epoch and eval functions` cell, and change IMAGE_SIZE=299 throughout the code (atleast for my system it had to be done). For other models it is fine. 
