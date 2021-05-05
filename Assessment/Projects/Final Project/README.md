# Final Project



Hints on what should go into this page (note each three of these sections are weighted evenly):

### Definition of problem being solved 

project overview:
The project aims at using deep learning model to recognize the type of vehicle on the mobile phone. The data come from Kaggle are in three labels and training in transfer learning models. After pretrain model, simple classifier, transfer training and retrain the model, our model can recognize the car and bus, but not good at truck.

research question:
Recognition the type of vehicle and alert the surrounding and recorder

data available:
The image is about types of vehicle. The data source is kaggle: The images are divided into Car, Bus and Truck, and those are also their labels.

outcomes anticipated:
 Connecting the Edge Impulse, I use my mobile phone to detect the type of vehicles, it can recognize the car and bus and have a relatively high accuracy, but bad performance on Truck

application design:

### Documentation of experiments and results 

After model the 1778 data, we got the result that the accuracy is 60%(actually is lower than the data before I eliminate the illegible photos), and the loss is 0.80. For improvement the model accuracy, we analyze the confusion matrix and found that Bus and Car Truck is easy to be recognized but the Truck has a bad result. The Truck is easy to be thought as Bus. Then I adjust the number of training cycles to 50, the learning rate to 0.0001. Then retrain the model for live classification. 


### Critical reflection and learning from experiments 
After pretrain model, simple classifier, transfer training and retrain the model, our model can recognize the car and bus, but not good at truck. The parameter are changed for making a better result, but there are some reason that influence device to detect the objective. Complexity of road and surrounding conditions and low image quality of light and object. So there are improvement needed in truck label. What’s more, to complete the project into a mature application, the wake word at the beginning will be replace with sound of car.




*You can choose what tools you use to write up and document your project - your final submission will be a pdf document being uploaded via Moodle, however we would also expect to see a link through to your GitHub repository where you data, results etc. are documented.*
