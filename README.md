# Neural-Network-training-for-webcam

Method for training Neural Networks on video footage, removing frames with faces as part of pre-process.

Using / adapting the code and method found here:
https://github.com/memo/webcam-pix2pix-tensorflow 

Which uses the TensorFlow machine learning library (https://www.tensorflow.org/) and pix2pix: https://github.com/phillipi/pix2pix 

Procedure:
1)	Convert video file to individual jpeg files using, omitting frames with faces detected using OpenCV and inbuilt Haar face detection based on this python script: https://github.com/oxcdx/computer_vision/blob/master/CAFFE_DNN/remove_faces_video.py 
2)	Crop and resize the frames to 256x256 resolution using ffmpeg
3)	Using pix2pix python script (https://github.com/memo/webcam-pix2pix-tensorflow/blob/master/preprocess.py) create a double side image 512x256 one side being the original, and the other side and edge detection filter (OpenCV canny) applied to image the original 
4)	Train using pix2pix python script (https://github.com/affinelayer/pix2pix-tensorflow/blob/master/pix2pix.py) 
5)	Import model and use with https://github.com/memo/webcam-pix2pix-tensorflow/blob/master/webcam-pix2pix.py 
