This is a list of Jupyter notebooks associated with StarNet to apply on SDSS APOGEE data.
 
They have been tested with python-2.7, some dependencies are not python-3 ready yet.

Required packages:
- numpy
- h5py
- random
- keras
- tensorflow or theano (backend for Keras)
- matplotlib
- seaborn
- sklearn
- jupyter
- vos

All those packages can be installed with pip.

```
pip install <package>...<package>
```
If you have the Python anaconda distribution, you can (except for `vos`) also install the packages not already installed with
```
conda install <package>...<package>
```

You can then clone this repository:
```
git clone https://github.com/astroai/starnet.git
cd starnet
jupyter notebook
```
A new browser tab should pop up, if not, copy and paste the given link into your in your browser.

Before starting any of the other notebooks, be sure to read through 1_Download_Data.ipynb to find out what data you need for which notebooks.
 Not all of the available data is completely necessary depending on where you would like to begin, but reading through the notebooks will provide a more complete understanding of the necessary steps taken when creating a neural network model.

Below is a description of the available notebooks:

1_Download_Data.ipynb
- provides descriptions of all of the available data, where the data is necessary, and the scripts needed to download the data
- files available for download in this notebook: apStar_visits_main.h5, apStar_combined_main.h5, training_set.h5, mean_and_std.npy, test_data.h5

2_Preprocessing_of_Training_Data.ipynb
- step by step preproceprocessing of the training data to create a training set
- required files to run this notebook: apStar_visits_main.h5
- files created in this notebooks: training_data.h5

3_Preprocessing_of_Test_Data.ipynb
- step by step preproceprocessing of test data to create a test set
- required files to run this notebook: apStar_combined_main.h5 and training_data.h5
- files created in this notebooks: mean_and_std.npy and test_data.h5

4_Train_Model.ipynb
- building model architecture, setting hyper-parameters, and training model using Keras
- required files to run this notebook: mean_and_std.npy and training_data.h5
- files created in this notebooks: starnet_cnn.h5

5_Test_Model.ipynb
- obtain model predictions for the test set and plot the results against ASPCAP DR13 labels
- required files to run this notebook: mean_and_std.npy, test_data.h5

6_Error_Propagation.ipynb
- obtain model statistical errors for a test set predictions
- required files to run this notebook: mean_and_std.npy, test_data.h5, starnet_cnn.h5
