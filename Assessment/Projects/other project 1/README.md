For the three months learning, I obtained the Complete knowledge system of deep learning and completely new experimental experience about net sensor.

I sorted out the models, knowledge and drawing methods applied in the learning process.






# Programming in google colab
## 1. Imports
tensorflow, numpy, matplotlib.pyplot, os, zipfile, random pandas, math, pathlib, matplotlib, scipy.misc
%matplotlib inline
from tensorflow import keras
from tensorflow.keras.optimizers import RMSprop
from tensorflow.keras.preprocessing.image import ImageDataGenerator
from shutil import copyfile
from six import BytesIO
from PIL import Image, ImageDraw, ImageFont
from six.moves.urllib.request import urlopen
from object_detection.utils import label_map_util
from object_detection.utils import visualization_utils as viz_utils
from object_detection.utils import ops as utils_ops

## 2. Load the data
### 2.1 Arrary
xs = np.array([-1.0, 0.0, 1.0, 2.0, 3.0, 4.0], dtype=float)
ys = np.array([-2.0, 1.0, 4.0, 7.0, 10.0, 13.0], dtype=float)
### 2.2 Load from mnist
(training_images, training_labels), (test_images, test_labels) = mnist.load_data()
### 2.3 Get from github
!git clone --depth 1 https://github.com/tensorflow/models
### 2.4 Upload from local dataset
upload = files_load()
### 2.5 Get from website
!wget -- no-check-certificated

## 3. Model
### 3.1 Keras, optimizer='sgd', loss='mean_squared_error'
model = tf.keras.Sequential()
model.add(tf.keras.Input(shape=(1,)))
model.add(tf.keras.layers.Dense(1,))
model.compile(optimizer='sgd', loss='mean_squared_error')
model.fit(xs, ys, epochs=200)

### 3.2 Keras, Flatten-Dense-Dense, activation=tf.nn.relu, activation=tf.nn.softmax
model = tf.keras.models.Sequential([
tf.keras.layers.Flatten(input_shape=(28, 28)), 
tf.keras.layers.Dense(128, activation=tf.nn.relu), 
tf.keras.layers.Dense(10, activation=tf.nn.softmax)])

### 3.3 Keras, Conv2D-Maxpooling-Flatten-Dense-Dense, activation=tf.nn.relu, activation=softmax
model = tf.keras.models.Sequential([
    tf.keras.layers.Conv2D(64, (3,3), activation='relu', input_shape=(28, 28, 1)),
    tf.keras.layers.MaxPooling2D(2, 2),
    tf.keras.layers.Conv2D(64, (3,3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2,2),
    tf.keras.layers.Flatten(),
    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.Dense(10, activation='softmax')
])
model.summary()

### 3.4 Keras, Conv2D-Maxpooling-Flatten-Dense-Dense, activation=tf.nn.relu, activation=sigmoid
model = tf.keras.models.Sequential([
    tf.keras.layers.Conv2D(16, (3, 3), activation='relu', input_shape=(150, 150, 3)),
    tf.keras.layers.MaxPooling2D(2, 2),
    tf.keras.layers.Conv2D(32, (3, 3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2, 2),
    tf.keras.layers.Conv2D(64, (3, 3), activation='relu'),
    tf.keras.layers.MaxPooling2D(2, 2),
    tf.keras.layers.Flatten(),
    tf.keras.layers.Dense(512, activation='relu'),
    tf.keras.layers.Dense(1, activation='sigmoid')
])

model.compile(optimizer=RMSprop(lr=0.0001), loss='binary_crossentropy', metrics=['acc'])
model.summary()

## 4. Processing Data
### 4.1 Normalize
training_images  = training_images / 255.0
test_images = test_images / 255.0
### 4.2 Split the data in training and testing
Sample = []
TRAIN_SPLIT =  int(0.6 * SAMPLES)
TEST_SPLIT = int(0.2 * SAMPLES + TRAIN_SPLIT)

x_train, x_test, x_validate = np.split(x_values, [TRAIN_SPLIT, TEST_SPLIT])
y_train, y_test, y_validate = np.split(y_values, [TRAIN_SPLIT, TEST_SPLIT])

### 4.3 Organize image data
def load_image_into_numpy_array(path):
image = None
  if(path.startswith('http')):
    response = urlopen(path)
    image_data = response.read()
    image_data = BytesIO(image_data)
    image = Image.open(image_data)
  else:
    image_data = tf.io.gfile.GFile(path, 'rb').read()
    image = Image.open(BytesIO(image_data))

  (im_width, im_height) = image.size
  return np.array(image.getdata()).reshape(
      (1, im_height, im_width, 3)).astype(np.uint8)

ALL_MODELS = {
## 5.Plot 


plt.imshow(training_images[sample], cmap='gray')


## 6.Other tips(about handling label and Dataset)
### 6.3 check the directionary
try:
    os.mkdir('/tmp/cats-v-dogs')
    os.mkdir('/tmp/cats-v-dogs/training')
except OSError:
    pass
### 6.4 Path
import os
MODELS_DIR = 'models/'
if not os.path.exists(MODELS_DIR):
    os.mkdir(MODELS_DIR)
MODEL_TF = MODELS_DIR + 'model'
MODEL_NO_QUANT_TFLITE = MODELS_DIR + 'model_no_quant.tflite'
MODEL_TFLITE = MODELS_DIR + 'model.tflite'
MODEL_TFLITE_MICRO = MODELS_DIR + 'model.cc'
### 6.5 Seed and reproducable
seed = 1337
np.random.seed(seed)
tf.random.set_seed(seed)
### 6.6 Add noise
y_values += 0.1 * np.random.randn(*y_values.shape)



# Audrino and C++
Generate a TensorFlow Lite Model
quantization
## Install xxd if it is not available
!apt-get update && apt-get -qq install xxd
## Convert to a C source file, i.e, a TensorFlow Lite for Microcontrollers model
!xxd -i {MODEL_TFLITE} > {MODEL_TFLITE_MICRO}
## Print the C source file
!cat {MODEL_TFLITE_MICRO}
