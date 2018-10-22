# EC601-TensorFlow-Practice
The project is aimed to use different machine learning models by TensorFlow and training a neural network to classify the type of galaxies. Deep space galaxies could be generally defined as spiral galaxy with apparent arms and elliptical galaxy with 


Training source acquisition

The image download process is implemented by google-image-download. The library could be download by "pip install google_images_download". 

The usage of google_images_download requires Chrome web browser and the instructions are based on command line tool.

Downloading images with certain key world, using the following command:
$ googleimagesdownload -k [argument] -l [number] (default number is set as 100)

If you want to download more than 100 pictures, try downloading Chromedriver with Selenium. Selenium is a open source web browser API, download the correct form of Chromedriver corresponding with you system in:
https://sites.google.com/a/chromium.org/chromedriver/downloads

Add "'--chromedriver' + [path to the chromedriver]" behind the downloading instruction.

For further instructions, visit https://github.com/hardikvasa/google-images-download or try:
$ googleimagesdownload -h

Now as different species of pictures are downloaded, we need to check if all the pictures are classified into correct folder. Some of the picture downloaded might not be relevant.





TensorFlow training instruction

The example code could be download from:
$ mkdir ~/example_code
$ cd ~/example_code
$ curl -LO https://github.com/tensorflow/hub/raw/master/examples/image_retraining/retrain.py

After the download, you can train your classified photo by:
$ python retrain.py --image_dir [path to your training source folder]
Or:
$ python retrain.py -h 
, for more training options.

The training result could be visualized by Tensorboard using the following command:
$ tensorboard --logdir /tmp/retrain_logs

Using the trained model

curl -LO https://github.com/tensorflow/tensorflow/raw/master/tensorflow/examples/label_image/label_image.py
python label_image.py \
--graph=/tmp/output_graph.pb --labels=/tmp/output_labels.txt \
--input_layer=Placeholder \
--output_layer=final_result \
--image=$[path to target image]

Trying different models
If the trained result is not exact, more models can be used in training by:
python retrain.py \
    --image_dir ~/flower_photos \
    --tfhub_module [model url]
More Tensorflow could be found on https://tfhub.dev/s?module-type=image-feature-vector.

