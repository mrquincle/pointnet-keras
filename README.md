# Classification

All corresponding .h5 files can be found under PrepData (for training) and PrepData_test for testing. This makes it possible to run it from https://colab.research.google.com.

You can experiment with it from the command line, open a new Notebook. Go to "Edit" - "Notebook settings" and select a GPU for acceleration.

Now download the code and the data from github (this takes a while because the files are big: > 50 MB).

    !git clone github.com:mrquincle/pointnet-keras.git

Now you can run the script immediately from the command line as well:

    !cd pointnet-keras && python3 train_cls.py

No need to install anything, no python3, no keras, no tensorflow, no numpy, no matplotlib, no h5py. It is an amazing world. :-D

Accuracy rate should be at around 82.5% (not as good as in the original implementation). I've to check this still, first five epochs:

    
    
    Using TensorFlow backend.
    2018-09-06 16:32:46.147706: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:897] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
    2018-09-06 16:32:46.148321: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1405] Found device 0 with properties: 
    name: Tesla K80 major: 3 minor: 7 memoryClockRate(GHz): 0.8235
    pciBusID: 0000:00:04.0
    totalMemory: 11.17GiB freeMemory: 11.10GiB
    2018-09-06 16:32:46.148368: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1484] Adding visible gpu devices: 0
    2018-09-06 16:32:46.612035: I tensorflow/core/common_runtime/gpu/gpu_device.cc:965] Device interconnect StreamExecutor with strength 1 edge matrix:
    2018-09-06 16:32:46.612117: I tensorflow/core/common_runtime/gpu/gpu_device.cc:971]      0 
    2018-09-06 16:32:46.612145: I tensorflow/core/common_runtime/gpu/gpu_device.cc:984] 0:   N 
    2018-09-06 16:32:46.612476: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1097] Created TensorFlow device (/job:localhost/replica:0/task:0/device:GPU:0 with 10759 MB memory) -> physical GPU (device: 0, name: Tesla K80, pci bus id: 0000:00:04.0, compute capability: 3.7)
    _________________________________________________________________
    Layer (type)                 Output Shape              Param #   
    =================================================================
    input_1 (InputLayer)         (None, 2048, 3)           0         
    _________________________________________________________________
    lambda_1 (Lambda)            (None, 2048, 3)           0         
    _________________________________________________________________
    conv1d_4 (Conv1D)            (None, 2048, 64)          256       
    _________________________________________________________________
    batch_normalization_6 (Batch (None, 2048, 64)          256       
    _________________________________________________________________
    conv1d_5 (Conv1D)            (None, 2048, 64)          4160      
    _________________________________________________________________
    batch_normalization_7 (Batch (None, 2048, 64)          256       
    _________________________________________________________________
    lambda_2 (Lambda)            (None, 2048, 64)          0         
    _________________________________________________________________
    conv1d_9 (Conv1D)            (None, 2048, 64)          4160      
    _________________________________________________________________
    batch_normalization_13 (Batc (None, 2048, 64)          256       
    _________________________________________________________________
    conv1d_10 (Conv1D)           (None, 2048, 128)         8320      
    _________________________________________________________________
    batch_normalization_14 (Batc (None, 2048, 128)         512       
    _________________________________________________________________
    conv1d_11 (Conv1D)           (None, 2048, 1024)        132096    
    _________________________________________________________________
    batch_normalization_15 (Batc (None, 2048, 1024)        4096      
    _________________________________________________________________
    max_pooling1d_3 (MaxPooling1 (None, 1, 1024)           0         
    _________________________________________________________________
    dense_7 (Dense)              (None, 1, 512)            524800    
    _________________________________________________________________
    batch_normalization_16 (Batc (None, 1, 512)            2048      
    _________________________________________________________________
    dropout_1 (Dropout)          (None, 1, 512)            0         
    _________________________________________________________________
    dense_8 (Dense)              (None, 1, 256)            131328    
    _________________________________________________________________
    batch_normalization_17 (Batc (None, 1, 256)            1024      
    _________________________________________________________________
    dropout_2 (Dropout)          (None, 1, 256)            0         
    _________________________________________________________________
    dense_9 (Dense)              (None, 1, 40)             10280     
    _________________________________________________________________
    flatten_1 (Flatten)          (None, 40)                0         
    =================================================================
    Total params: 823,848
    Trainable params: 819,624
    Non-trainable params: 4,224
    _________________________________________________________________
    None
    /content/pointnet-keras/PrepData
    ['ply_data_train1.h5', 'ply_data_train2.h5', 'ply_data_train4.h5', 'ply_data_train0.h5', 'ply_data_train3.h5']
    /content/pointnet-keras/PrepData_test
    ['ply_data_test0.h5', 'ply_data_test1.h5']
    Epoch 1/1
    9840/9840 [==============================] - 163s 17ms/step - loss: 3.3870 - acc: 0.2481
    Current epoch is:1
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 2.1239 - acc: 0.4228
    Current epoch is:2
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.7355 - acc: 0.5086
    Current epoch is:3
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.5330 - acc: 0.5547
    Current epoch is:4
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.4365 - acc: 0.5827
    Current epoch is:5
    2468/2468 [==============================] - 22s 9ms/step
    Test loss:  1.332594810080876
    Test accuracy:  0.5818476499189628
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.3695 - acc: 0.6003
    Current epoch is:6
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.3249 - acc: 0.6131
    Current epoch is:7
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.2833 - acc: 0.6251
    Current epoch is:8
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 1.2731 - acc: 0.6268
    Current epoch is:9
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.2265 - acc: 0.6435
    Current epoch is:10
    2468/2468 [==============================] - 21s 9ms/step
    Test loss:  1.0989031633256514
    Test accuracy:  0.6778768233387358
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.1875 - acc: 0.6503
    Current epoch is:11
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.1818 - acc: 0.6486
    Current epoch is:12
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.1856 - acc: 0.6498
    Current epoch is:13
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.1963 - acc: 0.6484
    Current epoch is:14
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 1.1427 - acc: 0.6674
    Current epoch is:15
    2468/2468 [==============================] - 21s 9ms/step
    Test loss:  1.1275335424723076
    Test accuracy:  0.6539708265802269
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 1.1377 - acc: 0.6644
    Current epoch is:16
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 1.1210 - acc: 0.6696
    Current epoch is:17
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.1057 - acc: 0.6701
    Current epoch is:18
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.1050 - acc: 0.6763
    Current epoch is:19
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 1.0693 - acc: 0.6849
    Current epoch is:20
    2468/2468 [==============================] - 21s 9ms/step
    Test loss:  1.0298815214073638
    Test accuracy:  0.690032414910859
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 1.0755 - acc: 0.6869
    Current epoch is:21
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.0649 - acc: 0.6850
    Current epoch is:22
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.0544 - acc: 0.6911
    Current epoch is:23
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.0457 - acc: 0.6898
    Current epoch is:24
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 1.0178 - acc: 0.6941
    Current epoch is:25
    2468/2468 [==============================] - 21s 9ms/step
    Test loss:  0.9236245159198632
    Test accuracy:  0.7236628849270664
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.0155 - acc: 0.6952
    Current epoch is:26
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.0333 - acc: 0.6980
    Current epoch is:27
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.0116 - acc: 0.6983
    Current epoch is:28
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.0196 - acc: 0.6998
    Current epoch is:29
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9939 - acc: 0.7047
    Current epoch is:30
    2468/2468 [==============================] - 21s 9ms/step
    Test loss:  0.8844803368832729
    Test accuracy:  0.723257698541329
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 1.0088 - acc: 0.7041
    Current epoch is:31
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9890 - acc: 0.7063
    Current epoch is:32
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9752 - acc: 0.7098
    Current epoch is:33
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9741 - acc: 0.7047
    Current epoch is:34
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9649 - acc: 0.7113
    Current epoch is:35
    2468/2468 [==============================] - 21s 9ms/step
    Test loss:  0.7037434272673373
    Test accuracy:  0.7852512155591572
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 0.9795 - acc: 0.7117
    Current epoch is:36
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 0.9792 - acc: 0.7111
    Current epoch is:37
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9953 - acc: 0.7046
    Current epoch is:38
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9590 - acc: 0.7132
    Current epoch is:39
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9632 - acc: 0.7141
    Current epoch is:40
    2468/2468 [==============================] - 21s 9ms/step
    Test loss:  0.854645596910721
    Test accuracy:  0.7325769854132901
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9826 - acc: 0.7078
    Current epoch is:41
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 0.9722 - acc: 0.7141
    Current epoch is:42
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9579 - acc: 0.7116
    Current epoch is:43
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9496 - acc: 0.7152
    Current epoch is:44
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9405 - acc: 0.7213
    Current epoch is:45
    2468/2468 [==============================] - 21s 9ms/step
    Test loss:  0.783388625087769
    Test accuracy:  0.7662074554294975
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9296 - acc: 0.7270
    Current epoch is:46
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 0.9385 - acc: 0.7202
    Current epoch is:47
    Epoch 1/1
    9840/9840 [==============================] - 160s 16ms/step - loss: 0.9342 - acc: 0.7221
    Current epoch is:48
    Epoch 1/1
    9840/9840 [==============================] - 159s 16ms/step - loss: 0.9306 - acc: 0.7238
    Current epoch is:49
    2468/2468 [==============================] - 21s 9ms/step
    Test loss:  0.8954283279190187
    Test accuracy:  0.7293354943273906
    
    

# Original Sources

Sources: Original [tensorflow implementation](https://github.com/charlesq34/pointnet) and [Keras implementation](https://github.com/garyli1019/pointnet-keras).

Official package requirements if doing everything from scratch: Python3.6, keras, tensorflow, numpy, matplotlib, h5py

