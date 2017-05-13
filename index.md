---
title       : Analysis of Size-Biased Mitochondria Data
subtitle    : 
author1     : Yin-Ting Chou
author2     : "Advisor: Aaron Rendahl"
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : mathjax           # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## <u>Overview</u>
1. Story about Size-Biased Data
2. Scientific Background for Mitochondria
3. Goals for this project: 
    * Whether Properties of mitochondria are different by locations. 
    * Suggestions on sampling scheme for future research. 
4. How Size-Biased Mitochondria Data came from? (Sampling Process)
5. Simulation Study 
6. Permutation Hypothesis Test and Boostrapping Confidence Interval 
7. Conclusion
8. Discussion 

--- .class #id 

## <u>Story about Size-Biased Data</u>
<br />
<br />
<img src="assets/img/fishingnet.jpg" style="width:480px;height:300px;">
<img src="assets/img/mall.jpg" style="width:480px;height:300px;">

--- .class #id 

## <u>Scientific Background for Mitochondria</u>
<center>
<img src="assets/img/muscle.jpg" style="width:700px">
</center>

--- .class #id 

## <u>Goals for this project: </u>

1. Whether Properties (area, perimeter, circularity and aspect ratio) of mitochondria are different by locations (proximal, middle and distal end). 
2. Suggestions on sampling scheme for future research. 

<center>
<img src="assets/img/location_cartoon.png" style="width:600px">
</center>

--- .class #id 

## <u>Sampling Process - 1</u>
* A young muscle fiber cell was magnifired to 166 different images by using Transmission Electron Microscope (TEM). 
* Those falls in <b>" { "</b> are defined as beging in <b>Proximal end</b>, in <b>" [ "</b> are being in <b>Distal end</b>, and the rest are being in <b>Middle part</b>.
</br><br />
<img src="assets/img/cell.png" style="width:400px">
<img src="assets/img/location.png" style="width:400px">

--- .class #id 

## <u>Sampling Process - 2</u>
* For each location, divide images into two groups: Subsarcolemmanl and Interfibrillar group. 
* In each group, randomly pick one image.

--- .class #id 

## <u>Sampling Process - 3</u>
* In each image, randomly pick <b>20 mitochondria</b>. 
* Generate a list of random coordinates. 
* Pick the mitochondria whose area in the photo includes one or more generated coordinates. 
</br><br/>
<center>
<img src="assets/img/mitochondria.png" style="width:350px">
</center>

--- .class #id 

## <u>Raw Data</u>


<iframe src="dat.html" allowtransparency="true"></iframe>

--- .class #id 

## <u>Problems</u>
1. It is not random sample. 
2. The larger mitochondria are easier to be picked in our sample. 
3. It is size-biased! 

--- .class #id 

## <u>Goals for this project: </u>
1. <font color="red"> What is the appropriate estimator for the size-biased data? </font> <br />
<font color = "green"><b>A: Simulation Study.</b></font>

2. Whether Properties (area, perimeter, circularity and aspect ratio) of mitochondria are different by locations (proximal, middle and distal end). <br />
<font color = "green"><b>A: Permutation Test and Boostrapping Confidence Interval.</b></font>

3. Suggestions on sampling scheme for future research.<br />
<font color = "green"><b>A: Based on the Simulation Study. </b></font>

--- .class #id 

## <u>Data Exploration: </u>
* <b>Area $({\mu m}^{2})$:</b> <br />
  The area occupied by a mitochondrion in an image. 
* <b>Perimeter $(\mu m)$:</b> <br />
  The length of the boundary of a mitochondrion in an image.
* <b>Circularity: </b><br />
Circularity is equal to $\frac{4 \pi Area}{Perimeter^2}$. <br /> 
(Measuring the resemblance of a mitochondrion to a circle. The range of circularity is     between 0 and 1.  1 means a perfect circle.)
* <b>Aspect Ratio:</b> <br />
  Aspect Ratio is equal to $\frac{Length}{Width}$. <br />
  (If $AR \leq 2$, it is considered short; if $2 < AR \leq 4$, intermediate; if $AR > 4$, long.)

--- &twocol #id 

## <u>Data Exploration: Area</u>


*** =left
<iframe src="hist_a.html" allowtransparency="true"></iframe>

*** =right
<iframe src="box_a.html" allowtransparency="true"></iframe>

--- &twocol #id 

## <u>Data Exploration: Perimeter</u>



*** =left
<iframe src="hist_p.html" allowtransparency="true"></iframe>

*** =right
<iframe src="box_p.html" allowtransparency="true"></iframe>

--- &twocol #id 

## <u>Data Exploration: Circularity</u>



*** =left
<iframe src="hist_c.html" allowtransparency="true"></iframe>

*** =right
<iframe src="box_c.html" allowtransparency="true"></iframe>

--- &twocol #id 

## <u>Data Exploration: Aspect Ratio</u>


*** =left
<iframe src="hist_ar.html" allowtransparency="true"></iframe>

*** =right
<iframe src="box_ar.html" allowtransparency="true"></iframe>

--- &twocol #id 

## <u>Data Exploration: Scatter Plots</u>
Perimeter, Circularity and Aspect Ratio


<iframe src="scatter.html"></iframe>

--- &twocol #id 
## <u>Weighted Distribution</u>
Cox (1962) proposed an idea of Weighted Distribution,
$${f}^{\ast}(x)=\frac{w(x)f(x)}{{E}_{f}(w(x))}$$

--- &twocol 
## <u>Candidate Estimators</u>

*** =left width:65%
* <b>Area:</b> 
  1. Arithmetic Mean (AM)
  2. Weighted Mean (WM)
  3. Maxima Likelihood Estimator (MLE)
  
* <b>Perimeter:</b>
  1. Arithmetic Mean (AM)
  2. Weighted Mean (WM)
  3. Delta Method Estimator (DME)

*** =right width:35%

<iframe src="scatter_p.html"></iframe>

--- &twocol 
## <u>Candidate Estimators</u>

*** =left width:55%
* <b>Circularity:</b>
  1. Arithmetic Mean (AM)

* <b>Aspect Ratio:</b>
  1. Arithmetic Mean (AM)

*** =right width:45%

<iframe src="scatter_c_ar.html"></iframe>

