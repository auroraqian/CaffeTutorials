# CaffeTutorials
http://developer.download.nvidia.com/embedded/L4T/r23_Release_v1.0/NVIDIA_Jetson_TX1_Developer_Kit_User_Guide.pdf

Remember to unselect “Compile CUDA samples"

- How to install CUDA on NVIDIA Jetson TX 1:   http://www.slothparadise.com/how-to-install-cuda-on-nvidia-jetson-tx1/
- Install Caffe from scratch : https://github.com/BVLC/caffe/wiki/Install-Caffe-on-EC2-from-scratch-(Ubuntu,-CUDA-7,-cuDNN)

Caffe

- Compile error about google: protobuf https://github.com/BVLC/caffe/issues/19
- https://github.com/google/protobuf
- compile error: kEmptyString is not a member of protobuf: solution: install protobuf 2.6


     But then I need to install protobuf 2.5/2.6

-      http://www.csrdu.org/nauman/2014/01/23/geting-started-with-hadoop-2-2-0-building/

-      Then when encounter error during make, just try to install the package that is not found!
    - Need to configure the make file again!
        - http://yongyuan.name/blog/problems-when-configing-caffe.html
    - Forgot to install mkl…:http://blog.sciencenet.cn/blog-1583812-841855.html
- But make mnist test failed
    - https://github.com//BVLC/caffe/issues/1298  change the size of 1T
- TUTORIALS!!!!
    - http://www.jimblog.net/2015/08/caffe-tutorial-part-1-basic-feedforward.html
    - http://caffe.berkeleyvision.org/gathered/examples/mnist.html
- 2016.03.12
    - when ~/caffe-master$ sudo sh examples/mnist/create_mnist.sh
    - encounter libcudart.so.7.0:campt p[em shared object file: No such file or directory

        - solved by looking at http://www.slothparadise.com/how-to-install-cuda-on-nvidia-jetson-tx1/ and removing lines that overwrite the LD_LIBRARY_PATH line
    - explaning about CNN : http://blog.csdn.net/dark_scope/article/details/9495505
    - http://blog.csdn.net/dark_scope/article/details/9495505
    - http://deeplearning.stanford.edu/wiki/index.php/Feature_extraction_using_convolution
    - http://www.cnblogs.com/tornadomeet/archive/2013/03/25/2980357.html
    - http://openclassroom.stanford.edu/MainFolder/VideoPage.php?course=MachineLearning&video=01.3-Introduction-SupervisedLearning&speed=100
- LeNet
    - http://deeplearning.net/tutorial/lenet.html
- ML-stanford(GOOD STUFF)
    - http://ufldl.stanford.edu/tutorial/supervised/FeatureExtractionUsingConvolution/
- Linear Regression

- Still don’t understand why convolution layer work..
- 2016.03.21
    - learn how to use the trained CNN
        - https://www.oreilly.com/learning/how-to-build-and-run-your-first-deep-learning-network !!!!!!
        - http://www.joyofdata.de/blog/neural-networks-with-caffe-on-the-gpu/
        - http://www.exaptive.com/blog/how-i-made-a-neural-network-web-application-in-an-hour
        - http://caffe.berkeleyvision.org/gathered/examples/imagenet.html (brewing Imagenet)
        - http://image-net.org/tutorials/cvpr2015/getting_started.pdf
        - http://image-net.org/tutorials/cvpr2015/getting_started.pdf
        - install Pycaffe
            - http://installing-caffe-the-right-way.wikidot.com/start!!! (follow this webpage and everything works)
            - http://sunshineatnoon.github.io/How-to-install-caffe/ !!!!!
            - can’t import caffe under python : https://github.com/NVIDIA/DIGITS/issues/216
        - classify image
            - https://github.com/BVLC/caffe/pull/2359/commits/dd3a5f9268ca3bdf19a17760bd6f568e21c1b521
        - General helpful discussion
            - https://github.com/BVLC/caffe/issues/729
- 20160404
    - nice tutorial about CNN : http://www.wildml.com/2015/11/understanding-convolutional-neural-networks-for-nlp/
