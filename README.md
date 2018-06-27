This Fork
---------

This fork is an update the original code (see description below) to make it compatible with Python 3.6 and Tensorflow 1.8.0.

Original Description
--------------------

# Sanskrit compound segmentation using seq2seq model 
Code for the paper titled ['Building a Word Segmenter for Sanskrit Overnight'](https://arxiv.org/abs/1802.06185)

Instructions
============

Pre-requisites
--------------
The following python packages are required to be installed:
* Tensorflow: https://www.tensorflow.org/, tensorflow version 0.12.1 was used for this project. 

File organization
-------------------------------------------
* Data is located in data/.
* Logs generated by tensorflow summarywriter is stored in logs/.
* Models which are trained are stored in models/. Before training make sure the folders logs/ and models/ are created.

Training
--------
The file train.py can be used to train the model.
The file test.py can be used to test the model.

Data
-------------------------------------------
data/ folder contains all the data used for the segmentation task.

All the .txt files are already tokenized using sentencepiece, the m.vocab and m.model files are the onces generated by sentencepiece and they can be used to tokenize any other data with the same vocabulary.

All .txt files contain data which are separeted by a new line(\n).

### Training data: 
* dcs_data_input_train_sent.txt file contains the input sentences used for training. 
* dcs_data_output_train_sent.txt file contains the output words(segmented forms of input) used for training.

### Testing data: 
* dcs_data_input_test_sent.txt file contains the input sentences used for testing. 
* dcs_data_output_test_sent.txt file contains the output words(segmented forms of input) used for testing.

Once the train.py file is run, it creates various other files for word2id, id2word, ... more details are provided in the utils/data_loader.py file.

Testing on other data
-------------------------------------------
To test on your your own data, create a file with all the sentences that are to segmented, one sentence per line and run the unsupervised segmenter(sentencepiece) using the m.vocab and m.model files present in the utils/ folder.
Also, create another file with ground truth outputs again tokenized with sentencepiece.
If you only intend to get the output from the model and not compare it with your ground truth data, then keep an empty file with same number of lines as the input data file.

Then modify the test.py with the appropriate path and run it.

Contact
--------
If you face any problem running the code or have any suggestions please open an issue or mail me at vikas.challaram@gmail.com
