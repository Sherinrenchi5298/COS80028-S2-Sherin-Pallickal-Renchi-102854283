# Abstract
The detection of software vulnerabilities is an important security research problem. However, existing solutions are subjective to the expertise of humans who manually define features and often miss many vulnerabilities (i.e., incurring high false-negative rate). This presentation showcases the design and implementation of deep learning-based vulnerability detection systems to relieve human experts from the tedious and subjective task of manually defining features as well as to produce more effective vulnerability detection systems. The vulnerabilities that are detected are buffer errors and resource management errors in software. An approach called code gadgets [1] is used, which represents software programs and then transforms them into vectors. A code gadget is the number of lines of code that are semantically related to each other. The approach then demonstrates the identification of vulnerabilities in different software products. The attendees will learn how deep-learning methods are more than just an improvement over the traditional vulnerability detection systems.

* Detects exploitable code in C/C++
* Uses N-grams and deep learning with LSTMs to train detection model
* Invents idea of code gadgets for semantically-related code
* Code gadgets are vectorized for input to neural network
[Training/testing set for this project includes existing code gadgets and vulnerability classification]
* Trained on two vulnerability types, Paper and GitHub


## Outline

* Preparing the environment by providing instructions (in Linux, windows, and mac) for installing software and dependencies: pandas, gensim, Keras, TensorFlow, and sklearn packages.
* Git repo installation instructions of the dataset (list of various instructions) that captures the vulnerable software (shared apriori) – buffer error and resource management errors.
* C++ code containing vulnerabilities
* Deep Learning algorithm that will be used BLSTM
* Train and Test Deep learning model on the dataset provided
* Git downloadable python code for this

### 
* •	To run program, use this command: python vuldeepecker.py [gadget_file], where gadget_file is one of the text files containing a gadget set
*	Program has 3 parts:
*	Performing gadget "cleaning"
*	Remove comments, string/character literals
*	Replacing all user-defined variables and functions with VAR# and FUN#, respectively
*	The # is an integer identifying the user-defined variable/function within the gadget
*	Note: this identifier only applies within the scope of the gadget
*	Vectorize gadget
*	Gadgets are parsed, tokenized, and transformed to vectors of embeddings
*	Vectors are normalized to a constant length through either truncation or padding
*	Train and test neural model
*	Gadget vectors are used as input to train the neural model
*	Data is split into training set and testing set
*	Neural model is trained, tested, and accuracy is reported
#### Code files
##### Interface_blstm.ipynb
*		Interface to project, uses functionality from other code files
*		Fetches each gadget, cleans, buffers, trains Word2Vec model, vectorizes, passes to neural net
##### cleaning_gadget.ipynb
*		For each gadget, replaces all user variables with "VAR#" and user functions with "FUN#"
*		Removes content from string and character literals
##### vectorize_gadget,ipynb
*		Converts gadgets into vectors
*		Tokenizes gadget (converts to symbols, operators, keywords)
*		Uses Word2Vec to convert tokens to embeddings
*		Combines token embeddings in a gadget to create 2D gadget vector
##### blstm.ipynb
*		Defines Bidirectional Long Short Term Memory neural network for training/prediction of vulnerabilities
*		Gets gadget vectors as input
*		Implements functions for both training and testing the model
*		Uses parameters defined in VulDeePecker paper
##### lstm.ipynb
*		Defines Long Short Term Memory neural network for training/prediction of vulnerabilities
*		Gets gadget vectors as input
*		Implements functions for both training and testing the model
*		Uses parameters defined in VulDeePecker paper (some standard parameter is used)

