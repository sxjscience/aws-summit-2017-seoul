AWS Seoul Summit 2017 Demos
---------------------------
Demo codes in our presentation about MXNet in AWS Seoul Summit 2017

| File Name        | Description |
| ------------- |:-------------:|
| mxnet-logistic_regression_diabetes.ipynb | The logistic regression example |
| mxnet-2hidden_fnn_diabetes.ipynb | The classification example using FNN with 2 hidden layers |
| mxnet-mnist_deep_cnn.ipynb | Example of classifying MNIST digits with a CNN |
| mxnet-seq2seq.ipynb        | The sequence-to-sequence learning example |
| mxnet_seq2seq_cudnn_speed.py | The MXNet side script that uses cudnn accelerated LSTM for seq2seq model |
| mxnet_seq2seq_native_speed.py | The MXNet side script that uses the native implemented LSTM for seq2seq model |
| keras_seq2seq_speed.py     | The Keras side script for seq2seq model |

You can preview all the notebooks here or using in https://nbviewer.jupyter.org/github/sxjscience/aws-summit-2017-seoul/tree/master/. Also, you can refer to the code and youtube tutorials in https://github.com/hunkim/DeepLearningZeroToAll for more explanation.

For the speed comparison, we use these commands:

MXNet with CUDNN accelerated LSTM
```bash
python3 mxnet_seq2seq_cudnn_speed.py
```

MXNet with native LSTM
```bash
python3 mxnet_seq2seq_native_speed.py
```

Keras 2.0.3 with TensorFlow Backend (TensorFlow version 1.0.1)
```bash
KERAS_BACKEND=tensorflow python3 keras_seq2seq_speed.py
```

Keras 2.0.3 with the Theano backend (Theano version 0.9)
```bash
KERAS_BACKEND=theano python3 keras_seq2seq_speed.py
```

We use a single GeForce GTX 1080 GPU + CUDNN V5.1

| Implementation | Time spent |
| -------------- |:----------:|
| MXNet with CUDNN LSTM | 5.34s |
| MXNet with native LSTM |16.96s |
| Keras with TF backend | 125.59s |
| Keras with Theano backend | 66.24s |

Also for the Theano speed test, I've run the script twice to eliminate the compilation time.
