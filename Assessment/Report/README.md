# Report title goes here

Yang Yifan, https://github.com/Yang-Yifan921/Assessment0018 / link to Edge Impulse projects

## Introduction
Urban transport is keeping developing and sensor technology can help us build a more convienent and lovable society. I want using deep learning to recognize the car is coming and their shape. So there are two parts. The first goal is to remind people disable and little animals  that there is a vehicle coming with light  flicker. And second part is detect the type of vehicle, which can help city management.
Where it will be used? It can be applied in the parking lot and undeveloped area.
The original of the come from my undergraduate dissertation, which is about detect the distribution of car-sharing(also new energy-driving ) in temporal-sptatial. I found that there are lock of a efficient way to calculate the type and the number of car in the parking. What’s more, because it is two-seat type so the the parking space is not used effectively in a normal scale position. So I think if we can use such tiny sensor to collect data, maybe it can not only effectively improve the traffic efficiency, but also help to analyze the urban land use problem. 


## Research Question

Recognition the type of vehicle and alert the surrounding and recorder


## Application Overview
Thinking back to the various application diagrams you have seen through the module - how would you describe an overview of the building blocks of your project - how do they connect, what do the component parts include.

*probably ~200 words and a diagram is usually good to convey your design!*

## Data

The image is about types of vehicle. The data source is kaggle: The images are divided into Car, Bus and Truck, and those are also their labels. 

During the experiment, the accuracy is not satisfied is a obvious problem. So, I recollected the data. More than download from Kaggle, I also search for high-definition car pictures with typical features. Because of the high complexity of the color and elements of the image, I filter out the samples with wrong labels one by one for each type of data.
In the process of data cleaning, it is found that the original sample contains a variety of car shapes, which may be because the samples are also collected through deep learning, so there are some errors. In the data processing, as human brain recognition, it will be difficult to distinguish the specific types, too (even if there are only three kinds), such as two-tier bus and large vans, car and truck which only showing head. Through comparison and summary, it is considered that the following factors interfere with model learning: the diversity of vehicle shape and type; Complexity of road and surrounding conditions and low image quality of light and object.



## Model
This is a Deep Learning project! What model architecture did you use? Did you try different ones? Why did you choose the ones you did?

*probably ~200 words and a diagram is usually good to describe your model!*

## Experiments
What experiments did you run to test your project? What parameters did you change? How did you measure performance? Did you write any scripts to evaluate performance? Did you use any tools to evaluate performance? Do you have graphs of results? 

*probably ~300 words and graphs and tables are usually good to convey your results!*

## Results and Observations
Synthesis the main results and observations you made from building the project. Did it work perfectly? Why not? What worked and what didn't? Why? What would you do next if you had more time?  

*probably ~300 words and remember images and diagrams bring results to life!*

## Bibliography
*If you added any references then add them in here using this format:*

1. Last name, First initial. (Year published). Title. Edition. (Only include the edition if it is not the first edition) City published: Publisher, Page(s). http://google.com

2. Last name, First initial. (Year published). Title. Edition. (Only include the edition if it is not the first edition) City published: Publisher, Page(s). http://google.com

----

## Declaration of Authorship

I, Yang Yifan, confirm that the work presented in this assessment is my own. Where information has been derived from other sources, I confirm that this has been indicated in the work.


*Yang Yifan*

29th, April, 2021 
