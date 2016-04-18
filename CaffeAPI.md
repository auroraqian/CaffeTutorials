Tutorial :
http://christopher5106.github.io/deep/learning/2015/09/04/Deep-learning-tutorial-on-Caffe-Technology.html

definition of layers: http://caffe.berkeleyvision.org/tutorial/layers.html
useful chinese note: http://blog.csdn.net/shadow_guo/article/details/50359532
BEST NOTE EVER!!!!!!!:http://nbviewer.jupyter.org/github/BVLC/caffe/blob/master/examples/00-classification.ipynb
About caffe.io.transformer : https://groups.google.com/forum/#!topic/caffe-users/kVDppVZo3jQ

About definition of convolution network

Convolution

- Layer type: Convolution
- CPU implementation: ./src/caffe/layers/convolution_layer.cpp
- CUDA GPU implementation: ./src/caffe/layers/convolution_layer.cu
- Parameters (ConvolutionParameter convolution_param)

    - Required

        - num_output (c_o): the number of filters
        - kernel_size (or kernel_h and kernel_w): specifies height and width of each filter
    - Strongly Recommended

        - weight_filler [default type: 'constant' value: 0]
    - Optional

        - bias_term [default true]: specifies whether to learn and apply a set of additive biases to the filter outputs
        - pad (or pad_h and pad_w) [default 0]: specifies the number of pixels to (implicitly) add to each side of the input
        - stride (or stride_h and stride_w) [default 1]: specifies the intervals at which to apply the filters to the input
        - group (g) [default 1]: If g > 1, we restrict the connectivity of each filter to a subset of the input. Specifically, the input and output channels are separated into g groups, and the iith output group channels will be only connected to the iith input group channels.
- Input

    - n * c_i * h_i * w_i
- Output

    - n * c_o * h_o * w_o, where h_o = (h_i + 2 * pad_h - kernel_h) / stride_h + 1 and w_olikewise.
- Sample (as seen in ./models/bvlc_reference_caffenet/train_val.prototxt)
- layer {
  name: "conv1"
  type: "Convolution"
  bottom: "data"
  top: "conv1"
  # learning rate and decay multipliers for the filters
  param { lr_mult: 1 decay_mult: 1 }
  # learning rate and decay multipliers for the biases
  param { lr_mult: 2 decay_mult: 0 }
  convolution_param {
    num_output: 96     # learn 96 filters
    kernel_size: 11    # each filter is 11x11
    stride: 4          # step 4 pixels between each filter application
    weight_filler {
      type: "gaussian" # initialize the filters from a Gaussian
      std: 0.01        # distribution with stdev 0.01 (default mean: 0)
    }
    bias_filler {
      type: "constant" # initialize the biases to zero (0)
      value: 0
    }
  }
}
