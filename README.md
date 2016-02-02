Git repository for the preparation of the IJCV journal with title 'Extensive Experimental Survey on Facial Non-rigid Tracking'.

The files and a short explanation is included below. The files are in the order that they should be called in order to be consistent with the methodology in the code.

* train_shape_predictors_on_presaved_images_bb.ipynb : Trains the landmark localisation models on images from public datasets with pre-saved bounding boxes.
* run_online_tracking_by_detection.ipynb : Runs the (python) detectors (on the testset) and on top of them a landmark localisation method and exports the bounding boxes and the landmarks. 
* tracker_from_previous_all_methods. ipynb : Perform tracking from the previous frame (on the testset). 


The files that are running on the testset assume the following folder structure: 

```
path_base_testset
└───category1
    │
    └───frames
            │
            └───[name_of_clip]
                    │ [frame_name].[extension] (e.g. 000001.png)
                    │ [frame_name].[extension] (e.g. 000002.png)
                    │ ...
            │ ...
    │
    └───gt_landmarks  (not required for executing the code)
            │
            └───[name_of_clip]
                    │ [file_name].[extension] (e.g. 000001.pts)
                    │ ...
            │ ...
 └───category2
    │ ...
```

Apart from menpo [(menpo, menpodetect, menpofit)](https://github.com/menpo/menpo) the following packages are used: 
* workerbee ``` pip install workerbee```
* research_pyutils from [this repository](https://github.com/grigorisg9gr/pyutils).
 
