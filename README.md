# stool_consistency
## source 
this python script is based on the tensorflow for poets codelabs : [codelabs link] (https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/#0)
You will need to clone the repository : </br>
```git clone https://github.com/googlecodelabs/tensorflow-for-poets-2  ``` 
and then clone the stool_consistency repository in the scripts folder to get the updated script for training the poobao data set. 
## updates 
The changes made concern the addition of a kfold cross-validation and the use of scikitlearn library to generate the confusion matrix and the f1-measure on the validation set. 
No distorsion has been applied to the poobao image data set during the training step.
it is possible to run the retrain poobao script using the following parameters (used to retrain the poobao v1 model) : 
```
! python -m script.retrain_poobao \
--architecture="mobilenet_1.0_224" \
--image_dir="/data/training_set/" \
--output_graph_path=tf_files/output_folder/fold \
--output_labels_path=tf_files/output_folder/fold \
--summaries_dir_path=tf_files/training_summaries/fold \
--how_many_training_steps=650 \
--learning_rate=0.001 \
--kfold=10 \
--model_dir=tf_files/models \
--bottleneck_dir=tf_files/bottlenecks```
