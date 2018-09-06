# Classification

All corresponding .h5 files can be found under PrepData (for training) and PrepData_test for testing. This makes it possible to run it from https://colab.research.google.com.

You can experiment with it from the command line, open a new Notebook. Go to "Edit" - "Notebook settings" and select a GPU for acceleration.

Now download the code and the data from github (this takes a while because the files are big: > 50 MB).

    !git clone github.com:mrquincle/pointnet-keras.git

Now you can run the script immediately from the command line as well:

    !cd pointnet-keras && python3 train_cls.py

No need to install anything, no python3, no keras, no tensorflow, no numpy, no matplotlib, no h5py. It is an amazing world. :-D

Accuracy rate should be at around 82.5% (not as good as in the original implementation). I've to check this still, first five epochs:

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


# Original Sources

Sources: Original [tensorflow implementation](https://github.com/charlesq34/pointnet) and [Keras implementation](https://github.com/garyli1019/pointnet-keras).

Official package requirements if doing everything from scratch: Python3.6, keras, tensorflow, numpy, matplotlib, h5py

