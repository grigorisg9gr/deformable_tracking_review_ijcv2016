Git repository for the preparation of the IJCV journal with title [`A comprehensive performance evaluation of deformable face tracking in-the-wild`](https://arxiv.org/abs/1603.06015)

The files included here are the python files that will allow you to reproduce the results of the paper. The rest of the (MATLAB/C/C++) codes can be found in the sites mentioned in the paper. 

The purpose of the files is to provide an explanation along with the params used to train the optimal models, hence allowing the reproduction of the results or further investigation/dissemination of these models.

A brief explanation of each file is included below, however you are encouraged to browse through the notebooks, which include more detailed comments along with the code. 

* train_shape_predictors_on_presaved_images_bb.ipynb : Trains the landmark localisation models on images from public datasets with pre-saved bounding boxes.
* run_online_tracking_by_detection.ipynb : Runs the (python) detectors (on the testset) and on top of them a landmark localisation method and exports the bounding boxes and the landmarks. 
* tracker_from_previous_all_methods. ipynb : Perform tracking from the previous frame (on the testset). 


#### **Folder structure**
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

#### **Dependency**
Apart from menpo [(menpo, menpodetect, menpofit)](https://github.com/menpo/menpo) the following packages are used: 
* workerbee ``` pip install workerbee```
* research_pyutils from [this repository](https://github.com/grigorisg9gr/pyutils).

#### **Feedback**
If you do have any questions or improvements, feel free to open issues here or contribute right away. Feedback is always appreciated.
Due to the heavy development of menpo and its research purpose, often there are breaking changes. If you encounter a compatibility issue with the latest menpo releases, please get in touch and I will fix the issue. 

