# level-5-project
## Investigating Deep Transfer Learning with Handwritten Text Images


### This code is run on Google Colab.
It can be run locally but the Drive mounting code has to be removed from the top of each .ipynb file.
If run on Google Colab, must have access to Google Drive and mount Drive with code provided at the top of each file.

### Download dataset:
https://fki.tic.heia-fr.ch/databases/download-the-iam-handwriting-database
Download the following from the link:
data/sentences.tgz and data/xml.tgz

Save it in Google Drive in a folder called 'iam_dataset' after unzipping the downloaded .tgz files.
The path on Google Colab should be: /content/drive/MyDrive/iam_dataset/
If this is not the case, please change the data_path and save_path as necessary.

If at any point there is a memory error (e.g. CUDA ran out of memory) Restart Runtime in the Runtime menu and run the code again with Run All.

## Run the following in order:

### 1. iam_dataset_pre_processing.ipynb
Takes a very long time to pre-process the data, if you don't want to, use provided labelled_data.npy file and skip this step.
Save labelled_data.npy in the iam_dataset folder created in the Google Drive.

In each .ipynb file, set the data_path and save_path appropriately. If above instructions followed, the dataset as well as labelled_data.npy should be available in the path:
'/content/drive/MyDrive/iam_dataset/'

### 2. original_3_convs_model_node1.ipynb
To generate the fully trained model (takes very long to run.)
Use provided model_3_convs.pt to save time and produce best results as it has been run many times to produce the best results.
Set save_results to True to save the classification report
Set save_model to True to save model.


### 3. node_2_+_3.ipynb, within the file:
Toggle NODE variable, choose between 2, 3, and 23 to change data appropriately.
For each NODE setting, toggle fc, conv, and plain_inf variables by setting them to True each in turn
For example if fc set to True, ensure conv and plain_inf are set to False

Set save_model to True to save the transfer learned model, in each case
Set save_results to True to save the classification report.

After toggles set, select Run All in the Runtime menu option in Colab.



### 4. node_4.ipynb, within the file:
Toggle fc, conv, and plain_inf variables by setting them to True each in turn
For example if fc set to True, ensure conv and plain_inf are set to False

Set save_model to True to save the transfer learned model, in each case
Set save_results to True to save the classification report.

After toggles set, select Run All in the Runtime menu option in Colab.


### 5. node_5.ipynb, within the file:
Toggle fc, conv, and plain_inf variables by setting them to True each in turn
For example if fc set to True, ensure conv and plain_inf are set to False

Set save_model to True to save the transfer learned model, in each case
Set save_results to True to save the classification report.

After toggles set, select Run All in the Runtime menu option in Colab.


### 6. node_6_+_7.ipynb, within the file:
Toggle NODE variable, choose between 6 and 7 to change data appropriately.
For each NODE setting, toggle fc, conv, and plain_inf variables by setting them to True each in turn
For example if fc set to True, ensure conv and plain_inf are set to False

Set save_model to True to save the transfer learned model, in each case
Set save_results to True to save the classification report.

After toggles set, select Run All in the Runtime menu option in Colab.

### 7. Reuse_on_node_1.ipynb
Set model_node variable, choose between 2,3,4,5,6,7, and 23 (for model transfer learned from nodes 1 to 2 to 3)
Set fc_pi variable to either 'fc' or 'pi'

Set save_model to True to save the transfer learned model, in each case
Set save_results to True to save the classification report.

After toggles set, select Run All in the Runtime menu option in Colab.

### 8. ResNet18_model_trials.ipynb
Toggle pre_trained, train_on_node1, pre_trained_on_node1_use_on_node2 by setting them to True in turn - only one should be True in each turn, with others set to False
pre_trained to use model pre trained on ImageNet database and transfer learn on node 1, train_on_node1 trains the model on node 1 data, pre_trained_on_node1_use_on_node2 transfer learn on node 2

Set save_model to True to save the transfer learned model, in each case
Set save_results to True to save the classification report.

After toggles set, select Run All in the Runtime menu option in Colab.

### 9. Clustering_umaps_for_all_nodes.ipynb
Set model_node variable, choose between 1,2,3,4,5,6,7 and 23 (for model transfer learned from nodes 1 to 2 to 3)
Set fc_conv to either 'fc' or 'conv' to choose the appropriate transfer learned model from each node.

After toggles set, select Run All in the Runtime menu option in Colab.

### 10. temperature_scaling.ipynb
Ensure the temperature_scaling.py file is in the iam_dataset folder at the path: /content/drive/MyDrive/iam_dataset/temperature_scaling.py
This file has been obtained from: https://github.com/gpleiss/temperature_scaling

Set model_node variable, choose between 1,2,3,4,5,6,7 and 23 (for model transfer learned from nodes 1 to 2 to 3)
After toggles set, select Run All in the Runtime menu option in Colab.

### 11. uncertainty_distributions.ipynb
No need to set anything just run the file as below.
Select Run All in the Runtime menu option in Colab.

### 12. interpretability_gradcam_intgrad_saliency_maps.ipynb
This file applies three interpretability techniques on the original model.
If there is a model saved by the name model_3_convs.pt, this file can be run.
No variables to set, select Run All in the Runtime menu option in Colab.
