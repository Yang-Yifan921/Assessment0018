For the three months learning, I obtained the Complete knowledge system of deep learning and completely new experimental experience about net sensor.

I sorted out the models, knowledge and drawing methods applied in the learning process.






# Programming in google colab
## 1. Imports
tensorflow, numpy, matplotlib.pyplot, os, zipfile, random pandas, math, pathlib, matplotlib, scipy.misc

from tf import keras, from tf import 
## 2. Load the data
### 2.1 Arrary
xs = np.array([-1.0, 0.0, 1.0, 2.0, 3.0, 4.0], dtype=float)
ys = np.array([-2.0, 1.0, 4.0, 7.0, 10.0, 13.0], dtype=float)
### 2.2 Load from mnist
(training_images, training_labels), (test_images, test_labels) = mnist.load_data()
### 2.3 Get from github

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

### 3.3 
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


## 4. Processing Data
### 4.1 Normalize
training_images  = training_images / 255.0
test_images = test_images / 255.0


## 5.Plot 


plt.imshow(training_images[sample], cmap='gray')


## 6.Other tips(about handling label and Dataset)


# Audrino and C++



