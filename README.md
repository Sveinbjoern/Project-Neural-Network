# Project-Neural-Network

Small project for training neural networks on the MNIST dataset


To train a network: 

Either find a network in MyModels or make a new one. If you make a new model remember to add it to the list in create_empty_model in MyModels
Check if your loss function is in create_loss_function in in MyModels, if not add it.
Check if your optimizer is in create_optimizerin in MyModels, if not add it.

In the MainTraining.ipynb:

Run setup

Create a new model with:
CMM =  hf.model_manager( model_class = "modelTypeName", 
                     loss_function_name = "Lossfunction name",
                     optimizer_name = "Optimizer name",
                     optimizer_params = {"lr": 0.001},)
                            OR
Load an existing model:
CMM = hf.load_model_manager("modelFileName")

Load your data with a data loader

train with: stats = CMM.initiate_training( number_of_epochs, train_dataloader, test_dataloader)
stats are returned for ease of access.

save the model with: hf.save_model_manager(CMM, "001") The file will be stored in models\modelName001.pth

To visualize data:

run setup
load data
to load you own data add visualizer.add_stats("Name for the visualizer", hf.load_stats("modelsavepath.pth"), stats_type=1) 
#Use stat type 1 except for autoencoders type 2

Choose models to load data from
Not all visualization work with all data. The autoencoder for example has not accuracy data.

