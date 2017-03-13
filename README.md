Git repository associated with the IJCV journal [`A comprehensive performance evaluation of deformable face tracking in-the-wild`](https://ibug.doc.ic.ac.uk/media/uploads/documents/ijcv_deformable_tracking_review.pdf).

The purpose of the files in the repo is to provide a concrete sample of how the models described in the paper were trained/utilised, hence allowing the reproduction of the results or further investigation/dissemination of these models.

### **Table of contents**
1. [Brief explanation of file contents](#brief_intro)
2. [How to use these files](#how_to_use)
3. [Links for detectors/trackers utilised](#links)
4. [Folder structure](#structure)
5. [Dependencies](#dependencies)
6. [Feedback](#feedback)
7. [License](#license)


<a name="brief_intro"></a>
### **Brief explanation of file contents**
A brief explanation of each file is included below, however you are encouraged to browse through the notebooks, which include more detailed comments along with the code. In case you want to execute those, please ensure you follow the instructed folder/path format that is expected or modify the code to match your paths accordingly.

* train_shape_predictors_on_presaved_images_bb.ipynb : Trains the landmark localisation models on images from public datasets with pre-saved bounding boxes.
* run_online_tracking_by_detection.ipynb : Runs the (python) detectors (on the testset) and on top of them a landmark localisation method and exports the bounding boxes and the landmarks. 
* tracker_from_previous_all_methods.ipynb : Performs tracking from the previous frame (on the testset). 
* replicate_ijcv_top_curves.ipynb : Reproduces the top curves of the experimental section of the paper. You can add your ow methods and directly compare with the original results.


<a name="how_to_use"></a>
### **How to use these files**
As aforementioned, these are the revised codes for creating (part of ) the results for the journal. They should be used as a guideline to reproduce the results or build similar models for your purpose. They are not published as a pipeline that will be called sequentially, hence you should use with caution.

The links for the actual trackers/detectors are provided below, so you can download and experiment with those directly.


<a name="links"></a>
### **Links for detectors/trackers utilised**

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


<a name="structure"></a>
### **Folder structure**
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

<a name="dependencies"></a>
### **Dependencies**
Apart from menpo [(menpo, menpodetect, menpofit)](https://github.com/menpo/menpo) the following packages are used: 
* workerbee ``` pip install workerbee```
* research_pyutils from [this repository](https://github.com/grigorisg9gr/pyutils).

Workerbee is a package that was used to execute the per frame processing in parallel utilising condor.
The version [v0.6.2](https://github.com/menpo/menpo/tree/v0.6.2) of menpo project was the one that the code was originally developed on, however it was updated to follow the latest version of v0.7.5. If you want to run the code, you are encouraged to install the later menpo version of [v0.7.5](https://github.com/menpo/menpo/releases/tag/v0.7.5).


<a name="feedback"></a>
### **Feedback**
If you do have any questions or improvements, feel free to open issues here or contribute right away. Feedback is always appreciated.
Due to the heavy development of menpo and its research purpose, often there are breaking changes. If you encounter a compatibility issue with the latest menpo releases, feel free to raise an issue. 


<a name="license"></a>
### **License**
Apache 2, version 2.0, see [http://www.apache.org/licenses](http://www.apache.org/licenses/#2.0) for further details.

