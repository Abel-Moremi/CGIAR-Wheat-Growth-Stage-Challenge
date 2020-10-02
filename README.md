# CGIAR Wheat Growth Stage Challenge by [CGIAR Platform for Big Data in Agriculture](https://bigdata.cgiar.org/)

### INTRODUCTION

The [competition](https://zindi.africa/competitions/cgiar-wheat-growth-stage-challenge) is hosted on Zindi. It had compeditors from around the world. Used it as a great learning opportunity. Its a real world business problem.

[Picture-based insurance (PBI)](https://www.ifpri.org/project/PBInsurance) improves crop insurance for small scale farmers around the world, where images from a smartphone camera keep a record of a crop’s growth and record any damage events that will affect insurance payouts. PBI is a great way for insurers to verify events and to monitor crop growth, but it can also generate overwhelming amounts of data once images stream in from thousands of farmers.

### GOAL

For this competition, I had to automate one part of the data processing pipeline: estimating the growth stage of a wheat crop based on an image sent in by a farmer. The images are automatically cropped to show a section of the field. My model must take in an image and output a prediction for the growth stage of the wheat shown, on a scale from 1 (crop just showing) to 7 (mature crop). My solution has to operate on the input image ONLY - no additional data may be used.

### RESOURCES
Reference points I used to build this model;

- [FastAi Starter](https://colab.research.google.com/drive/1hjecqhFZVv21tY8qoO3PiJtY7acjFPEU?usp=sharing) Notebook by [@Johnowhitaker](https://zindi.africa/users/Johnowhitaker) from [Zindi](https://zindi.africa/competitions/cgiar-wheat-growth-stage-challenge/discussions/2903)
- [Starter Notebook](https://drive.google.com/drive/folders/1MJOzTC1rmrkRRlthTyv8vLk5Lb76hRpC) by [@KarimAmer](https://zindi.africa/users/KarimAmer/competitions) from [Zindi](https://zindi.africa/competitions/cgiar-wheat-growth-stage-challenge/discussions/2903)
- [Transfer learning for computer vision toturial](https://pytorch.org/tutorials/beginner/transfer_learning_tutorial.html) from official PyTorch docs 
