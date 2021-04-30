<h3>Objective</h3>
<p>The aim of this project is to automatically convert handwritten text into machine encoded text.</p>
<h4>Strategy </h4>
<p>The project has 4 major components: </p>
<ol>
<li>Preprocess image and text data</li>
<li>Implementation of CNN layers to extract features</li>
<li>Implementation of RNN (Bi-LSTM) layers to the sequence model</li>
<li>CTC_loss and CTC_decode</li>
</ol>
<h3>Dataset Description </h3>
<h6><a href="https://fki.tic.heia-fr.ch/databases/iam-handwriting-database#:~:text=The%20IAM%20Handwriting%20Database%20contains,1%5D%20at%20the%20ICDAR%201999.&text=The%20IAM%2Ddatabase%20as%20of,is%20described%20in%20%5B4%5D." target="_blank">Dataset: IAM Dataset</a> </h6>
<h6><a href="https://drive.google.com/file/d/1idCx6pr1ptmHrEHjbbiQxF4xoCZ9dNtv/view">Download word dataset here</a></h6>
<p>You will be using the IAM dataset for training and testing your model. We will use the words 
subset of the dataset, in which each image contains a word. The dataset contains over 8000 
images and their digital text.</p>
<p>This is a sample from text file,</p>
<p>a03-006-00-06 ok 156 1400 937 294 59 NN Foreign </p>
where, a03-006-00-06: is image location+ image id
 and Foreign: is actual word
<p>Image file contains one word in each image</p>

![test.png](attachment:test.png)
<h3>Task done: </h3>
<ol>
<li>Read the parser.txt file containing the image id and the respective word for that image 
and take the first 10000 instances for training and testing of the model</li>
<li>Images can be of different shape thus resize all your images to have the same shape (for 
example = (128,32))</li>
<li>Currently, the pixel values are between 0 to 255, normalize the images so that the pixel 
values are in range 0 to 1</li>
<li>Create a list of all characters and use the character’s index to encode the actual words 
into digits</li>
<li>Pad all the words to have a similar length</li>
<li>Split your dataset for training and testing</li>
<li>Create a model for training:</li>
<ol>
<li>Add several CNN layers to extract the sequence of features</li>
<li>Add Bi-LSTM layers to propagate through the sequence</li>
<li>Add a dense output layer with total number of neurons as (total characters + 1) and the activation as softmax.</li>
</ol>
<li>The output sequence from the output layer will be fed to the CTC layer.
</ol>

Final Result
![output.png](attachment:output.png)

<h3>References:<h3>
<ul>
<li>https://medium.com/swlh/learn-and-use-handwritten-line-text-recognition-using-deep-learning-with-tensorflow-b661434b5e3b</li>
<br>
<li>https://towardsdatascience.com/intuitively-understanding-connectionist-temporal-classification-3797e43a86c</li>
<br>
<li>ctc_batch_cost: https://www.tensorflow.org/api_docs/python/tf/keras/backend/ctc_batch_cost</li>
<br>
<li>ctc_decode: https://www.tensorflow.org/api_docs/python/tf/keras/backend/ctc</li>
</ul>
