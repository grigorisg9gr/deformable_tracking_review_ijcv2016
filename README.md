Git repository associated with the IJCV journal [`A comprehensive performance evaluation of deformable face tracking in-the-wild`](https://arxiv.org/abs/1603.06015).

The purpose of the files in the repo is to provide a concrete sample of how the models described in the paper were trained/utilised, hence allowing the reproduction of the results or further investigation/dissemination of these models.

A brief explanation of each file is included below, however you are encouraged to browse through the notebooks, which include more detailed comments along with the code.

* train_shape_predictors_on_presaved_images_bb.ipynb : Trains the landmark localisation models on images from public datasets with pre-saved bounding boxes.
* run_online_tracking_by_detection.ipynb : Runs the (python) detectors (on the testset) and on top of them a landmark localisation method and exports the bounding boxes and the landmarks. 
* tracker_from_previous_all_methods.ipynb : Perform tracking from the previous frame (on the testset). 

#### **Links for detectors/trackers utilised**

The various methods utilised in this paper can be found in:

* detectors:

| Name    |  Link                                     |
|:---------:|-------------------------------------------|
| DPM     | https://github.com/menpo/ffld2            |
| HR-TF   | https://www.cs.cmu.edu/~peiyunh/tiny/     |
| MTCNN   | https://goo.gl/4BMGeR                     |
| NPD     | https://goo.gl/dRXp8d                     |
| SS-DPM  | https://www.ics.uci.edu/~xzhu/face        |
| SVM+HOG | https://github.com/davisking/dlib         |
| VJ      | http://opencv.org                         |
| VPHR    | http://cvit.iiit.ac.in/projects/exemplar/ |

* trackers:

me     | Link                                  |
|:----------:|---------------------------------------|
| CAMSHIFT | http://opencv.org                     |
| CCOT     | https://goo.gl/Rnf73K                 |
| CMT      | https://github.com/gnebehay/CppMT     |
| DF       | http://goo.gl/YmG6W4                  |
| DLSSVM   | https://goo.gl/m4ro8x                 |
| DSST     | https://github.com/davisking/dlib     |
| FCT      | http://goo.gl/Ujc5B0                  |
| HDT      | https://goo.gl/9KgteR                 |
| IVT      | http://goo.gl/WtbOIX                  |
| KCF      | https://github.com/joaofaro/KCFcpp    |
| LCT      | https://goo.gl/8kaO7T                 |
| LRST     | http://goo.gl/ZC9JbQ                  |
| MDNET    | https://github.com/HyeonseobNam/MDNet |
| MEEM     | https://goo.gl/Bj6typ                 |
| MIL      | http://opencv.org                     |
| ORIA     | https://goo.gl/RT3zNC                 |
| PF       | https://goo.gl/tSZcAg                 |
| RPT      | https://github.com/ihpdep/rpt         |
| SIAM-OXF | https://goo.gl/sjGgVj                 |
| SPOT     | http://visionlab.tudelft.nl/spot      |
| SPT      | https://goo.gl/EOquai                 |
| SRDCF    | https://goo.gl/Q9d1O5                 |
| STAPLE   | https://github.com/bertinetto/staple  |
| STCL     | https://goo.gl/l29dQg                 |
| STRUCK   | http://goo.gl/gLR93b                  |
| TGPR     | https://goo.gl/EBw0WI                 |
| TLD      | https://github.com/zk00006/OpenTLD    |



#### **Folder structure**
The afore-mentioned code assumes the following folder structure for the 300-VW testset: 

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

Workerbee is a package that was used to execute the per frame processing in parallel utilising condor.
The version [v0.6.2](https://github.com/menpo/menpo/tree/v0.6.2) of menpo project was the one that the code was originally developed on, however it was updated to follow the latest version of v0.7.0.


#### **Feedback**
If you do have any questions or improvements, feel free to open issues here or contribute right away. Feedback is always appreciated.
Due to the heavy development of menpo and its research purpose, often there are breaking changes. If you encounter a compatibility issue with the latest menpo releases, please get in touch and I will fix the issue. 

