# VideoShift
This repo contains information about 'VideoShift' benchmark and download instructions for its three datasets: HOMAGE, InteractADL, and WAGE.

## Overview

The VideoShift Benchmark is designed to evaluate and compare various models on their distribution shift ability in video data. This benchmark includes three multiview video sub-datasets: HOMAGE, InteractADL, and WAGE. Each dataset includes dense atomic actions and scen-graph annotations, designed to capture fine-grained information in videos. Specifically, the benchmark assesses the adatability from household datasets (HOMAGE and InteractADL) to the workplace dataset (WAGE), facilitating both in-domain and out-of-domain adaptation challenges.

## Datasets

The HOMAGE dataset is focused on household activities with single actor performing individual activities in each video, typically around 1 minute long.
The InteractADL dataset covers household activities with two actors per video, each video lasting around 10 minutes featuring multiple activities. 
The WAGE dataset is focused on workplace acitivities and  simulates workplace environments with single actors performing individual activities in videos that are approximately 1 minute long.
We release WAGE under CC BY-NC-ND 4.0 license. With the help of the authors of HOMAGE and InteractADL, these datasets are also released under the same license. 

## Download Links
The original datasets include the following:
- [homage.zip](https://videoshift-benchmark-original.s3.amazonaws.com/homage.zip) (169GB)
- [interactadl.zip](https://videoshift-benchmark-original.s3.amazonaws.com/interactadl.zip) (134GB)
- [wage.zip](https://videoshift-benchmark-original.s3.amazonaws.com/wage.zip) (52GB)
- [videoshift_benchmark.zip](https://videoshift-benchmark-original.s3.amazonaws.com/videoshift_benchmark.zip) (356GB) contains all of the three datasets above.
The modified datasets used in training the baseline VideoShift benchmark include the following:
- [homage.zip](https://videoshift-benchmark.s3.amazonaws.com/homage.zip) (228GB)
- [interactadl.zip](https://videoshift-benchmark.s3.amazonaws.com/interactadl.zip) (46GB)
- [wage.zip](https://videoshift-benchmark.s3.amazonaws.com/wage.zip) (1.6GB)
- [videoshift_benchmark.zip](https://videoshift-benchmark.s3.amazonaws.com/videoshift_benchmark.zip) (275G) contains all of the three datasets above.

## Folder Structure Details
Each sub-dataset includes the following:
- ego-view videos
- third-person-view videos
- activity labels
- atomic action labels
- scene-graph annotations

The folder structures slightly vary among the sub-datasets.

The whole structure of the benchmark is shown below.

```
videoshift_benchmark/
├── LICENSE.txt
├── HOMAGE/
│   ├── annotations/
│   │   ├── atomic_actions/
│   │   │   ├── p0002/
│   │   │   │   ├── p0002_r000_a000_aa.json # p[task_id]_r[room_id]_a[action_id]
│   │   │   ├── ...
│   │   ├── scene_graph_annotations/
│   │   │   ├── p0002/
│   │   │   │   ├── p0002_r000_v001_a000_sg.json # p[task_id]_r[room_id]_v[view_id]_a[action_id]
│   │   │   ├── ...
│   ├── ego-and-3rd-person-view/ # view_id:0 represents ego-view
│   │   ├── p0002/
│   │   │   ├── p0002_r000_v000_a000.mkv # p[task_id]_r[room_id]_v[view_id]_a[action_id]
│   │   │   ├── p0002_r000_v000_a001.mkv
│   │   │   ├── ...
│   │   ├── p0003/
│   │   │   ├── p0003_r000_v000_a000.mkv
│   │   │   ├── p0003_r000_v000_a001.mkv
│   │   │   ├── ...
│   ├── activity_lists/ # activity labels
│   │   ├── format_list_files.md
│   │   ├── train_list.csv
│   │   ├── test_list.csv
├── InteractADL/
│   ├── floor_map.png
│   ├── videofile_viewID.xlsx
│   ├── annotations/
│   │   ├── activity/
│   │   │   ├── task01_person1_activity.json
│   │   │   ├── task01_person2_activity.json
│   │   │   ├── task02_person1_activity.json
│   │   │   ├── task02_person2_activity.json
│   │   │   ├── ...
│   │   ├── atomic_action/
│   │   │   ├── task01_person1_atomic.json
│   │   │   ├── task01_person2_atomic.json
│   │   │   ├── task02_person1_atomic.json
│   │   │   ├── task02_person2_atomic.json
│   │   │   ├── ...
│   │   ├── scene_graph/
│   │   │   ├── task01/
│   │   │   │   ├── task_1_person_1_eat_dinnereat_foods_7_6-eat_dinner_eat_foods
│   │   │   │   ├── task_1_person_2_defrost_thaw_frozen_food_3_15-defrost_thaw_frozen_food
│   │   │   │   ├── ...
│   │   │   ├── task02/
│   │   │   │   ├── ...
│   │   │   ├── ...
│   ├── ego-view/
│   │   ├── task01/
│   │   │   ├── Person 1.mp4
│   │   │   ├── Person 2.mp4
│   │   ├── task02/
│   │   │   ├── Person 1.mp4
│   │   │   ├── Person 2.mp4
│   │   ├── ...
│   ├── 3rd-person-view/
│   │   ├── task01/
│   │   │   ├── task1_040322071368__rgb.mp4 # task[task_id]_[camera_id]
│   │   │   ├── task1_048522070826__rgb.mp4
│   │   │   ├── ...
│   │   ├── task02/
│   │   │   ├── task2_040322071368__rgb.mp4
│   │   │   ├── task2_042222070526__rgb.mp4
│   │   │   ├── ...
│   │   ├── ...
├── WAGE/
│   ├── activity-class-list.xlsx # activity labels
│   ├── atomic-action/
│   │   ├── data001_001_048522070875.json # data[person_id]_[recording_id]_[camera_id]
│   │   ├── data001_002_048522070875.json
│   │   ├── ...
│   ├── scene-graph/
│   │   ├── data001_001_048522070875/
│   │   │   ├── data001_001_048522070875_check_device_000.json
│   │   │   ├── data001_001_048522070875_put_bag_000.json
│   │   │   ├── ...
│   │   ├── data001_002_047422071051/
│   │   │   ├── data001_002_047422071051_check_device_000.json
│   │   │   ├── data001_002_047422071051_put_device_000.json
│   │   │   ├── ...
│   ├── ego-view/
│   │   ├── data001_001.MP4
│   │   ├── data001_002.MP4
│   │   ├── ...
│   ├── 3rd-person-view/
│   │   ├── data001_001_048522070875.mp4
│   │   ├── data001_001_048522075341.mp4
│   │   ├── ...
│   │   ├── data002_001_047422071051.mp4
│   │   ├── data002_001_048522070875.mp4
│   │   ├── ...
```

## Citation
xxx

## Contact
kyuragi dot yuta at jp dot panasonic dot com

## License

All sub-datasets (HOMAGE, InteractADL, and WAGE) are released under the CC BY-NC-ND 4.0. Please refer to the license file.

---

By providing these datasets, we aim to support the research community in developing and testing robust video analysis models. We encourage feedback and collaboration to further enhance the VideoShift Benchmark.