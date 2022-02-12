# MILD: Multi-Index hashing for Loop closure Detection.
Official implementation for MILD: Multi-Index hashing for Loop closure Detection. [Paper](https://arxiv.org/abs/1702.08780)

This is a project from LuVision SIGMA, Tsinghua University. Visit our website for more interesting works: http://www.luvision.net/

## License
This project is released under the [GPLv3 license](LICENSE). We only allow free use for academic use. For commercial use, please contact us to negotiate a different license by: `fanglu at tsinghua.edu.cn`

## Citing
If you find our code useful, please kindly cite our paper:

```bibtex
@INPROCEEDINGS{8019479,
  author={Han, Lei and Fang, Lu},
  booktitle={2017 IEEE International Conference on Multimedia and Expo (ICME)}, 
  title={MILD: Multi-index hashing for appearance based loop closure detection}, 
  year={2017},
  volume={},
  number={},
  pages={139-144},
  doi={10.1109/ICME.2017.8019479}}
```

# Prerequisites  ################################################################

Ubuntu 14.04

cmake 3.2.0

OpenCV 3.1 http://xfloyd.net/blog/?p=987

eigen3

octave (optional, only used for evaluation)

# Installation ################################################################
$ mkdir build

$ cd build

$ cmake ..

$ make 



# Usage ##############################################################


./mild imagelist.txt settings.yaml

input:

imageList.txt: indicats the path of each input RGB image per line
settings.yaml: indicats the parameters used in loop closure detection

output:

output/imagelist/lcd_shared_flag.bin: detected loop closure are set as 1. To be used in the run_scritp.m to check the accuracy of the detected loop closure.
output/imagelist/lcd_shared_score_mild.bin: the image similarity calculated using MILD.
output/imagelist/relocalization_time_per_frame.bin: lcd time of each frame.

evluation: (based on MATLAB/OCTAVE)

evaluation('build/output/imageList_NewCollege/lcd_shared_flag.bin','build/output/imageList_NewCollege/lcd_shared_probability.bin','data/truthNewCollege.mat');
