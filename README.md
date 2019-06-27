# Multiple-Face-Recognition
OpenCV based face recognition system that can detect and recognize multiple faces in an image.

Here basically I used OpenCV for the entire work. But the main question is how to get the dataset? Well for that we created a file called face_datasets.py and this file uses openCV's methods to capture photos from each frame of the webcam. So we get our dataset from here.

After getting the dataset, we need a model to train it. But first of all we need to detect the faces and for that we used OpenCV's pre trained classifier(haarcascade_frontalface_default). We used Local Binary Patterns Histograms for face recognition. Local binary patterns are in short texture descriptor. 
So in OpenCV there are total 3 face recognition algorithms. The Eigenfaces and Fisherfaces just treat our data as a vector in a high dimensional image space and high dimensionality isn't good. Eigenfaces and Fisherfaces find a mathematical description of the most dominant features of the training set as a whole. LBPH analyzes each face in the training set separately and independently.
In LBPH each images is analyzed independently, while the eigenfaces method looks at the dataset as a whole. The LBPH method is somewhat simpler, in the sense that we characterize each image in the dataset locally; and when a new unknown image is provided, we perform the same analysis on it and compare the result to each of the images in the dataset. The way which we analyze the images is by characterizing the local patterns in each location in the image.
So that's why we chose the LBPH algorithm for our face recognition purpose.
Next we train this model using our obtained dataset. After that we save it and use it for our recognition purpose.

## Requirements

- Python 3.6
- OpenCV 3.3.0 or above
- Numpy 1.14.3 or above

## Main 3 steps of this project:

1. Gathering the dataset from webcam.(also you can skip it if you have the data already)
2. Train a model from the acquired dataset and save the model.
3. Use the trained model to classify faces in realtime.

## Steps to run this on your system.
This must work with OSX and Linux. I haven't tried windows yet.

**Step 1**: Create directories saved_model and training_data. Although it will be added automatically if you forget to create.
Run the face_datasets.py file on your terminal. Before running it set the **face_id** (on line 23) to some integer value for each time
you run it. This sets the labels.

**Step 2**: Start training the model with the obtained dataset by running the training.py.

**Step 3**: Run the face_recognition.py file to start detection. But before running that don't forget to change the names of ids from
line 59.(Some names are already set since I ran it)

See the results.

Reference: OpenCV Documentation
