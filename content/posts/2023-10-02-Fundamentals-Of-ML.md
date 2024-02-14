+++
title = "Fundamentals Of Linear Regression"
date = "2023-10-02"
summary = "The Very Basic Summary Of Linear Regression"
+++

# The Basics:
Machine Learing can be divided into two parts Supervised(Task Driven) and UnSupervised(Data Driven):
![](https://www.labellerr.com/blog/content/images/size/w1000/2023/02/bannerSupervised-vs.-Unsupervised-Learning-1.webp)

Now Let's Start with Linear Regression:

# Linear Regression

* Our Aim : To Find the Best fit line or get the minimal error
![](https://online.stat.psu.edu/stat462/sites/onlinecourses.science.psu.edu.stat462/files/02simple/heightweight/index.jpg)
![](https://miro.medium.com/v2/resize:fit:1304/1*fRBsGFTnefjErR3fEkRAIQ.png)

# OKay Now what about the Maths Behind it???
* Well it's nothing but your very on favourithe formula of slope of a line 
$ y = mx + c $
* where m is the slope or coefficient
* and c is the intercept
* Now wee'll also have a function of hypothesis let's see the function:
![](https://dataaspirant.files.wordpress.com/2014/09/vlcsnap-2014-09-23-23h30m27s241.png)
* Now we have also seen the cost function and so our main goal would be to minimize that

# The Gradient Descent
![](https://static.javatpoint.com/tutorial/machine-learning/images/gradient-descent-in-machine-learning1.png)
* If we move towards a negative gradient or away from the gradient of the function at the current point, it will give the local minimum of that function.
* Whenever we move towards a positive gradient or towards the gradient of the function at the current point, we will get the local maximum of that function.
* The main objective of using a gradient descent algorithm is to minimize the cost function using iteration.
![](https://www.ibm.com/content/dam/connectedassets-adobe-cms/worldwide-content/cdp/cf/ul/g/c2/0f/ICLH_Diagram_Batch_03_21-AI-ML-GradientDescent.component.simple-narrative-m.ts=1706296079680.png/content/adobe-cms/us/en/topics/gradient-descent/jcr:content/root/table_of_contents/body/content_section_styled/content-section-body/simple_narrative_1771421240/image)

# So the Outline will be

![](https://www.scribbr.com/wp-content/uploads/2020/02/simple-linear-regression-graph.png)