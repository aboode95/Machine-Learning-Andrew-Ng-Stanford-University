# Lecture 2: Linear Regression With One Variable

 

## Model Representation

### Notation:

 

**m** *= Number of training examples*

**x** *= "input" variable / features*

**y** *= "output" variable / "target" varible*

*(***x,y)** *= one training example*

(x^(i)^, y^(i)^) = i^th^ training example

**h** = hypothesis / function of x --> y

$\boldsymbol\theta$ = parameters of the model



![Machine generated alternative text: Training Set  Learning Algorithm  Size of  house  h  Estimated  price ](file:///C:/Users/shiha/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

 

**h** *is a function that maps from x's to y's*

 

#### How to represent h? 

$$
h_\theta(x) = \theta_0 + \theta_1x​
$$

Shorthand for![img](file:///C:/Users/shiha/AppData/Local/Temp/msohtmlclip1/01/clip_image003.png)

 

![Machine generated alternative text: = 00  Linear regression with one variable.  Univariate linear regression. ](file:///C:/Users/shiha/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

 

*In the above picture, an example of house prices. This is a Linear regression with one variable.*

 

![Machine generated alternative text: 00 + 01:r  00 = 1.5  01 0.5 ](file:///C:/Users/shiha/AppData/Local/Temp/msohtmlclip1/01/clip_image005.png)

In the above picture, an example of how $h_\theta(x)$ changes with $\theta_0$ and $\theta_1$



 #### Cost Function: To get the accurate prediction

Idea: Choose **training parameters** so that the **predicted value** is closer to the **actual answer** for our training examples (x,y).

*Or in other words: Choose $\theta_0$, $\theta_1$ so that $\boldsymbol{h_Q(x)}$ is close to **y** for our training examples (x,y).*

*Minimization problem:*
$$
\text{minimise }\theta_0, \theta_1: (h_\theta(x) - y)^2 \\
\text{minimise }\theta_0, \theta_1:  \sum\limits^m_{i=1}(h_\theta(x^{(i)}) - y^{(i)})^2 \\
\text{minimise }\theta_0, \theta_1:  \frac1{2m} \sum\limits^m_{i=1}(h_\theta(x^{(i)}) - y^{(i)})^2 \\
(\text{where, } h_\theta(x^{(i)}) = \theta_0 + \theta_1x^{(i)})
$$

**Note:** The $\frac1{m}$ comes from taking average of the sum and the $\frac12$ comes from "making the math bit easier".

##### Rewriting this function cleanly: the conventional way

$$
J(\theta_0, \theta_1) = \frac1{2m} \sum\limits^m_{i=1} ( h_\theta(x^{(i)})-y^{(i)})^2
$$

Cost Function is also called Squared error function.

**Why do we Square our error function?**

Because it is found to work really well with most problems and is widely used. Though there are more error functions/cost function

**Understanding what the math expression means:**

* Taking $\theta_1$as 0:
  The hypothesis becomes:

$$
h_\theta (x) = \theta_1x
$$

![image-20200606160634897](C:\Users\shiha\AppData\Roaming\Typora\typora-user-images\image-20200606160634897.png)

​	Here you see that $\theta_0=0$ simply means that the **$h(x)$ function passes through origin**.

- so,
  $$
  J(\theta_1) = \frac1{2m} \sum\limits^m_{i=1}(h_\theta(x^{(i)}) - y^{(i)})^2
  $$

- replacing $h_\theta(x^{(i)})$
  $$
  J(\theta_1) = \frac1{2m} \sum\limits^m_{i=1}(\theta_1x^{(i)} - y^{(i)})^2
  $$