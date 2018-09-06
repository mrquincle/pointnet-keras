# Classification

All corresponding .h5 files can be found under Prepdata (for training) and Prepdata_test for testing. This makes it possible to run it from https://colab.research.google.com.

You can experiment with it from the command line, open a new Notebook. Go to "Edit" - "Notebook settings" and select a GPU for acceleration.

Now download the code and the data from github (this takes a while because the files are big: > 50 MB).

    !git clone github.com:mrquincle/pointnet-keras.git

Now you can run the script immediately from the command line as well:

    !cd pointnet-keras && python3 train_cls.py

No need to install anything, no python3, no keras, no tensorflow, no numpy, no matplotlib, no h5py. It is an amazing world. :-D

Accuracy rate should be at around 82.5% (below original implementation). I've to check this.

# Original Sources

Sources: Original [tensorflow implementation](https://github.com/charlesq34/pointnet) and [Keras implementation](https://github.com/garyli1019/pointnet-keras).

Official package requirements if doing everything from scratch: Python3.6, keras, tensorflow, numpy, matplotlib, h5py

