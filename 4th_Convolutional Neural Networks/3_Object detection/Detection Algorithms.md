# Detection Algorithms

### 1. You are building a 3-class object classification and localization algorithm. The classes are: pedestrian (c=1), car (c=2), motorcycle (c=3). What should <img src="https://latex.codecogs.com/svg.image?y" title="y" /> be for the image below? Remember that “?” means “don’t care”, which means that the neural network loss function won’t care what the neural network gives for that component of the output. Recall <img src="https://latex.codecogs.com/svg.image?y&space;=&space;\left&space;[&space;p_c,&space;b_x,&space;b_y,&space;b_h,&space;b_w,&space;c_1,&space;c_2,&space;c_3&space;\right&space;]" title="y = \left [ p_c, b_x, b_y, b_h, b_w, c_1, c_2, c_3 \right ]" />  
<p align="center">
  <img width="70%" height="70%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/4th_Convolutional%20Neural%20Networks/3_Object%20detection/C4W3_Q_image/1.png">
</p>

- <img src="https://latex.codecogs.com/svg.image?y&space;=&space;\left&space;[&space;0,&space;?,?,?,?,?,?,?&space;\right&space;]" title="y = \left [ 0, ?,?,?,?,?,?,? \right ]" />
---

### 2. You are working on a factory automation task. Your system will see a can of soft-drink coming down a conveyor belt, and you want it to take a picture and decide whether (i) there is a soft-drink can in the image, and if so (ii) its bounding box. Since the soft-drink can is round, the bounding box is always square, and the soft drink can always appear as the same size in the image. There is at most one soft drink can in each image. Here’re some typical images in your training set:
<p align="center">
  <img width="70%" height="70%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/4th_Convolutional%20Neural%20Networks/3_Object%20detection/C4W3_Q_image/2.png">
</p>

What is the most appropriate set of output units for your neural network?

- Logistic unit, <img src="https://latex.codecogs.com/svg.image?b_x&space;and&space;b_y" title="b_x and b_y" />
---

### 3. If you build a neural network that inputs a picture of a person’s face and outputs N landmarks on the face (assume the input image always contains exactly one face), how many output units will the network have?
- 2N
---

### 4. When training one of the object detection systems described in lecture, you need a training set that contains many pictures of the object(s) you wish to detect. However, bounding boxes do not need to be provided in the training set, since the algorithm can learn to detect the objects by itself.
- False
> You need bounding boxes in the training set. Your loss function should try to match the predictions for the bounding boxes to the true bounding boxes from the training set. 
---

### 5. What is the IoU between these two boxes? The upper-left box is 2x2, and the lower-right box is 2x3. The overlapping region is 1x1. 
<p align="center">
  <img width="70%" height="70%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/4th_Convolutional%20Neural%20Networks/3_Object%20detection/C4W3_Q_image/5.png">
</p>

- 1/9
> The left box's area is 4 while the right box 's is 6. Their intersection's area is 1. So their union's area is 4 + 6 - 1 = 9 which leads to an intersection over union of 1/9.
---

### 6. Suppose you run non-max suppression on the predicted boxes above. The parameters you use for non-max suppression are that boxes with probability ≤ 0.4 are discarded, and the IoU threshold for deciding if two boxes overlap is 0.5. How many boxes will remain after non-max suppression?
<p align="center">
  <img width="70%" height="70%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/4th_Convolutional%20Neural%20Networks/3_Object%20detection/C4W3_Q_image/6.png">
</p>

- 5
---

### 7. Suppose you are using YOLO on a 19x19 grid, on a detection problem with 20 classes, and with 5 anchor boxes. During training, for each image you will need to construct an output volume <img src="https://latex.codecogs.com/svg.image?y" title="y" /> as the target value for the neural network; this corresponds to the last layer of the neural network. (<img src="https://latex.codecogs.com/svg.image?y" title="y" /> may include some “?”, or “don’t cares”). What is the dimension of this output volume?
- [x] 19x19x(5x25)
- [ ] 19x19x(25x20)
- [ ] 19x19x(5x20)
- [ ] 19x19x(20x25)
> you get a 19x19 grid where each cell encodes information about 5 boxes and each box is defined by a confidence probability (<img src="https://latex.codecogs.com/svg.image?p_c" title="p_c" />), 4 coordinates <img src="https://latex.codecogs.com/svg.image?(b_x,&space;b_y,&space;b_h,&space;b_w)" title="(b_x, b_y, b_h, b_w)" /> and classes <img src="https://latex.codecogs.com/svg.image?(c_1,...,&space;c_{20})" title="(c_1,..., c_{20})" />.
---

### 8. What is Semantic Segmentation?
- [x] Locating objects in an image by predicting each pixel as to which class it belongs to.
- [ ] Locating an object in an image belonging to a certain class by drawing a bounding box around it.
- [ ] Locating objects in an image belonging to different classes by drawing bounding boxes around them.

--- 
### 9. Using the concept of Transpose Convolution, fill in the values of X, Y and Z below. 
(padding = 1, stride = 2)

<u>Input</u>: 2x2

1|2
---|---
3|4

<u>Filter</u>: 3x3

1|0|-1
---|---|---
1|0|-1
1|0|-1

<u>Result</u>: 6x6

.|.|.|.|.|.
---|---|---|---|---|---
.|0|1|0|-2|.
.|0|X|0|Y|.
.|0|1|0|Z|.
.|0|1|0|-4|.
.|.|.|.|.|.

- X=2, Y=-6, Z=-4

> Regular convolution, you would take the filter and place it on top of the inputs and then multiply and sum up.
> 
> Transpose convolution, instead of placing the filter on the input, you would instead place a filter on the output.

> extra explanation #1
<p align="center">
  <img width="70%" height="70%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/4th_Convolutional%20Neural%20Networks/3_Object%20detection/C4W3_Q_image/9.jpg">
</p>

> extra explanation #2
<p align="center">
  <img width="70%" height="70%" src="https://github.com/RoBoTics-JHJ/Coursera_AndrewLectures/blob/main/4th_Convolutional%20Neural%20Networks/3_Object%20detection/C4W3_Q_image/9_1.jpg">
</p>

---

### 10. Suppose your input to an U-Net architecture is h x w x 3, where 3 denotes your number of channels (RGB). What will be the dimension of your output ?
- h x w x n, where number of output classes