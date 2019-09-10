% Artificial Intelligence Intro
% Simon Lau
% 11 Sep 2019

# Artificial Intelligence Intro

## Agenda

- Artificial Intelligence (not covered)
- Machine Learning
- Machine Learning II
- Deep Learning
- Deep Learning II
- Conclusion

## AI terms

![AI Terms](https://www.mytectra.com/media/wysiwyg/Blog/deep-learning.png)

## Another View

![AI Terms](https://miro.medium.com/max/1850/1*QJG2nMIqWHmLp2j4c0GVuQ.png)

## Caveat

- I am no expert
  - Only went for `1`{.c} course, no projects done
- Treating AI, Machine Learning, Deep Learning as black boxes
  - Tends to leads to claims which cannot be supported by the mathematics

# Machine Learning

## Machine Learning Types

### Algorithms

- Supervised (comes with answer)
- Unsupervised (no answer)
- Reinforcement Learning (not covered)

### Results

- Regression
  - Returns a continuous numerical value: `Number`{.javascript}
- Classification
  - Returns a label: `"Cat"? or "Dog"?`{.c}

## I need a home

- Block
- Street (Name)
- Storey
- (Floor) Area
- Lease (Commence Date)
- (Remaining) Lease
- (Resale) Price
- (Resale) Date

<https://services2.hdb.gov.sg/webapp/BB33RTIS/BB33SSearchWidget>

## Resale 4 Room in Woodlands

| Block | Street | Storey | Area | Lease | Remaining | Price |
| ----- | ------ | ------ | ---- | ----- | --------- | ----- |
| 679   | Ave 6  | 4 to 6 | 101  | 1998  | 77yr 11 m | 385k  |
| 782A  | Cres   | 7 to 9 | 92   | 2015  | 94yr 10 m | 385k  |
| 787E  | Cres   | 7 to 9 | 101  | 1997  | 77yr 2 m  | 332k  |
| 620   | Dr 52  | 4 to 6 | 92   | 1998  | 77yr 2 m  | 300k  |
| 683A  | Dr 62  | 1 to 3 | 104  | 2000  | 77yr 2 m  | 335k  |

## Which Algorithm

### Algorithms Type

- Supervised
- Unsupervised

### Results Type

- Regression
- Classification

## Features

- We call each column a **feature**
  - Block
  - Street (Name)
  - Storey
  - (Floor) Area
  - Lease (Commence Date)
  - (Remaining) Lease
  - (Resale) Price => this is **label** for numeric
    - Regression Supervised learning
  - (Resale) Date

## Model

Each Feature can be mapped to `A, B, C, D... etc` into a formula like:

$X_1 * A + X_2 * B + X_3 * C +.... = Price$

so this **model** becomes

X~1~ \* `679`{.c} + X~2~ \* `"Ave 6"`{.c} + X~3~ \* `"4 to 6"`{.c} + X~4~ \* `101`{.c} + X~5~ \* `1998`{.c} + X~6~ \* `"77yr 11 m"`{.c} = `385`{.c}k

X~1~, X~2~, X~3~ etc are called **weights**

## Data Transformation I

X~6~ \* `"77yr 11 m"`{.c}

makes no sense in the formula

We can change it from mixed to just months

`77 * 12 + 11 = 947`{.c} so we get X~6~ \* `947`{.c}

What about X~2~ \* `"Ave 6"`{.c}?

## Data Transformation II

X~2~ \* `"Ave 6"`{.c}

makes no sense in the formula

We can combine:

- Block
- Street (Name)

To give Postal Code `730679`{.c} so we get X~2~ \* `730679`{.c}

Is there anything _wrong_ with this approach?

## Training the model

X~1~ \* `730679`{.c} + X~3~ \* `4`{.c} + X~4~ \* `101`{.c} + X~5~ \* `1998`{.c} + X~6~ \* `947`{.c} = `385`{.c}k

- For training we are trying to identify the _weights_ X~1~, X~2~ ... etc
- For that to work, we feed the data in and adjust the _weights_ until they are stable and normalised (usually between `0 and 1`{.c})

## Model Weights

X~1~ \* `730679`{.c} + X~3~ \* `4`{.c} + X~4~ \* `101`{.c} + X~5~ \* `1998`{.c} + X~6~ \* `947`{.c} = `385`{.c}k

- Using numbers like `730679`{.c} means that
  - `365339`{.c} is about **half** of `730679`{.c}
- These represent postal codes
  - so they should be Categorical _feature_ where there is no ordering
    - Think like colours (Red, Green, Blue etc)

## Data Cleaning

- `NaN`{.javascript} values
- Missing values
- Standardisation (`String`{.java}: upper, lower or mixed)

## Storey vs Price

![Scatter Plot](https://miro.medium.com/max/1200/0*szXvH1a4ZQytyqhg.png){width=70% height=70%}

## Loss Function

![Mean Square Error](https://cdn-media-1.freecodecamp.org/images/MNskFmGPKuQfMLdmpkT-X7-8w2cJXulP3683){width=50% height=50%}

## Multi dimensional Equation

![Equation](https://cdn-media-1.freecodecamp.org/images/hmZydSW9YegiMVPWq2JBpOpai3CejzQpGkNG)

## Multi dimensional Loss Function

![3D plot](https://miro.medium.com/max/1200/0*ZaEKARNxNgB7-H3F.){width=70% height=70%}

## Gradient Descent

![Looking for the minimum of the formula](https://miro.medium.com/max/600/1*iNPHcCxIvcm7RwkRaMTx1g.jpeg)

## Convex vs Non-convex Function

![Local vs GLobal Minimal](https://miro.medium.com/max/463/0*GrBkYv2vodl_swFI.png)

## Learning Rate

![Big vs Small](https://miro.medium.com/max/1600/1*hGhRddOUV8h0pdQek8T35A.png)

## Underfitting, Overfitting

![Data](https://miro.medium.com/max/768/1*H7kHsf5oZy_KepJHTD6hMQ.png)

## Overfitting

![Data](https://miro.medium.com/max/778/1*ffYTFTzj_00JDciD9KV19Q.png)

## Underfitting

![Data](https://miro.medium.com/max/782/1*Gl5dciQc0H72vnZr5vIGqA.png)

## Feature Engineering I

What _feature_ can we add to this?

| Block | Street | Storey | Area | Lease | Remaining | Price |
| ----- | ------ | ------ | ---- | ----- | --------- | ----- |
| 679   | Ave 6  | 4 to 6 | 101  | 1998  | 77yr 11 m | 385k  |
| 782A  | Cres   | 7 to 9 | 92   | 2015  | 94yr 10 m | 385k  |
| 787E  | Cres   | 7 to 9 | 101  | 1997  | 77yr 2 m  | 332k  |
| 620   | Dr 52  | 4 to 6 | 92   | 1998  | 77yr 2 m  | 300k  |
| 683A  | Dr 62  | 1 to 3 | 104  | 2000  | 77yr 2 m  | 335k  |

## Feature Engineering II

- Distance to MRT and school
- High, Mid or Low Storey

## Feature Engineering III

- Distance to MRT and school
  - Convert Block and Street to (lat, lng)
  - Then calculate the distance
- High, Mid or Low Storey
  - Need to know how high is the original block
  - Then decide

# Machine Learning II

## Classification Types

- Binary Classification
- Multi Class Classification

![Can we use Regression for Binary Classification?](https://miro.medium.com/max/561/1*G6Rc1ytFxr11rZxXZKiOZg.png)

## Not useful

- For Binary Classification
  - Results must be either `0 or 1`{.c}
  - Regression might give `results > 1`{.c} or `< 0`{.c}
- So we use Sigmod function

![Sigmod](https://miro.medium.com/max/485/1*Xu7B5y9gp0iL5ooBj7LtWw.png)

## Support Vector Machines (SVM)

![Split this](https://miro.medium.com/max/989/0*8iRUPIB6XjkOSihP.)

## SVM Split I

![Bad line](https://miro.medium.com/max/989/0*uqvkhDvtLXy9lZG6.)

## SVM Split II

![Good line](https://miro.medium.com/max/989/0*_J_T8BQq8g46GJ6n.)

## Higher Dimensions

![Things look better in 3D](https://miro.medium.com/max/1592/0*ln9m5l2YUAe57R_T.png)

## SVM Plane

![Draw the hyperplane](https://miro.medium.com/max/1566/0*SYE5OjcSFe1MWdQC.png)

## K Nearest Neighbour (KNN)

![No parametric formula](https://miro.medium.com/max/440/0*chgrJFN_Y5S0QksO.)

## KNN nearest

![Which line to use?](https://miro.medium.com/max/400/0*M00nbLfTUSsmSoEM.)

## Decision Tree

![Titanic Survival](https://miro.medium.com/max/965/0*pZ0pgQT3i-CFPyaf.)

## Random Forest

![Ensemble learning](https://miro.medium.com/max/592/1*i0o8mjFfCn-uD79-F1Cqkw.png)

## Imbalanced dataset

![Undersampling vs Oversampling](https://miro.medium.com/max/725/0*49LgGsY4l09sNwcR.png)

# Deep Learning I

## Deep Learning Types

- Computer Vision (Pictures)
- Natural Language Processing (NLP - words) - Not covered
- Speech - not covered

## Machine Learning Model I

![Housing again](https://miro.medium.com/max/883/1*LlTIwE6h0l1Aoln2GlAGcw.png){width=70% height=70%}

## Machine Learning Model II

![More than 1 sets of weights](https://miro.medium.com/max/1485/1*hOemQF_v42KHlMyiqcQNyQ.png){width=60% height=60%}

## Machine Learning Model III

![Final Estimate](https://miro.medium.com/max/777/1*VeS0ziSjogCQThPYZh0TIQ.png){width=50% height=50%}

## Neuron

![Full view](https://miro.medium.com/max/895/1*Lt8RZaeQ6f6B_eA1oD32JQ.png){width=60% height=60%}

## Biology

![Biology vs artifical](https://miro.medium.com/max/1890/1*0UxcK0BoePVAeIdzeqEhzQ.png)

## Neural Network

![Simple vs Deep](https://miro.medium.com/max/690/1*dnvGC-PORSoCo7VXT3PV_A.png)

## How to process images

- Images made up of pixels matrix
- Each pixel is (Red, Green, Blue)

![Cat](https://cdn.pixabay.com/photo/2019/05/16/23/17/cat-4208584_960_720.jpg){height=96 width=72}

`=> [(123, 213, 87), (223, 113, 187)... ]`{.c}

## Too much info in images

![height=96 width=72](https://cdn.pixabay.com/photo/2019/05/16/23/17/cat-4208584_960_720.jpg){height=96 width=72}

`92 (Height) x 72 (Width) x 3 (Colours) = 20,730 features`{.c}

## Trying to use templates

![Averaging photos doesn't work](https://miro.medium.com/max/917/1*6o4FaHE9ehj_eN5HykKjSA.png)

## Identifying number 8

![Overview](https://miro.medium.com/max/977/1*b31hqXiBUjIXo2HSn_grFw.png){width=70% height=70%}

## Tunnel Vision

![Above Works](https://miro.medium.com/max/1202/1*5ciREAL7xdyXcD-cSRP7Jw.png)

![Above Fail](https://miro.medium.com/max/1185/1*b5jMTAiyVhOIB9hheXhMmA.png)

## Sliding window

![Left to right, top to bottom](https://miro.medium.com/max/950/1*bGBijVuJnTRj8025et0mcQ.gif)

## More Training Data

![Image Augmentation](https://miro.medium.com/max/1085/1*biD9eS5eB6zXzieonNk-VQ.png)

## Deeper Neural Network

![More complex](https://miro.medium.com/max/2256/1*wfmpsoFqWKC7VadjTJxwnQ.png)

## Child Image

![No Context](https://miro.medium.com/max/5146/1*v_06o9d5u4k2lp9cTHQUtg.jpeg){width=70% height=70%}

## Humans can tell

- The ground is covered in grass and concrete
- There is a child
- The child is sitting on a bouncy horse
- The bouncy horse is on top of the grass

## Break the image up

![Split](https://miro.medium.com/max/4585/1*xS7EugfgQHk68iph7GHpQg.png){width=70% height=70%}

## Feed 1 part

![Identify 1 part](https://miro.medium.com/max/758/1*84-TdHvtAHkfnzwa1ZsTVg.png)

## Save result

![](https://miro.medium.com/max/893/1*tpMqyjAFgsYWpvlNkZgFfw.png){width=50% height=50%}

## Downsampling

![Reduce image to simpler matrix](https://miro.medium.com/max/1047/1*1WWTbW9yyEJ69TF1rsPv4g.png)

## Max Pooling

![Pick the highest value](https://miro.medium.com/max/887/1*xOAroFiw9X0WSkCwgcIO6Q.png)

## Complete pipeline

![CNN](https://miro.medium.com/max/1589/1*tJ1Rkl5xw_5izEZXmNfh5Q.png)

# Deep Learning II

## 2 different people

![Will Ferrell vs Chad Smith](https://miro.medium.com/max/1920/1*l7zNW_4-afEOfP_mXxs75w.jpeg){width=70% height=70%}

## Humans are good at this

![Can you see a face?](https://miro.medium.com/max/580/1*HcwWLND2du14e-rzJ50tHA.jpeg)

## Steps in complex algo

![Let's walk through](https://miro.medium.com/max/1000/1*WxBM1lB5WzDjrDXYfi9gtw.gif)

## Change to Black and White

![Why Black and White?](https://miro.medium.com/max/511/1*osGdB2BNMThhk1rTwo07JA.jpeg){width=30% height=30%}

## Histogram of Oriented Gradients I

![Look at each pixel and those surrounding it](https://miro.medium.com/max/800/1*RZS05e_5XXQdofdRx1GvPA.gif)

## Histogram of Oriented Gradients II

![Draw an arrow towards the darkest pixel](https://miro.medium.com/max/500/1*WF54tQnH1Hgpoqk-Vtf9Lg.gif)

## Histogram of Oriented Gradients III

![Gradients, show the flow from light to dark](https://miro.medium.com/max/1000/1*oTdaElx_M-_z9c_iAwwqcw.gif)

Why do this?

## Histogram of Oriented Gradients IV

![Max pool 16 x 16 instead of 1 x 1](https://miro.medium.com/max/800/1*uHisafuUw0FOsoZA992Jdg.gif)

Normalise the image irregardless of lighting conditions

## Histogram of Oriented Gradients V

![Match Pattern](https://miro.medium.com/max/1162/1*6xgev0r-qn4oR88FrW6fiA.png){width=70% height=70%}

## Histogram of Oriented Gradients VI

![We can find faces](https://miro.medium.com/max/1200/1*dOtP6yl7d4c0oaR6NpfWVg.jpeg){width=70% height=70%}

## Same person Different Pose

![What do we do in this case?](https://miro.medium.com/max/956/1*x-rg0aSpKOer1JF-TejYUg.png)

## Landmarks

![68 specific points Face Landmark Estimation](https://miro.medium.com/max/414/1*AbEg31EgkbXSQehuNJBlWg.png)

<http://www.csc.kth.se/~vahidk/papers/KazemiCVPR14.pdf>

## Transform using landmarks

![](https://miro.medium.com/max/1908/1*igEzGcFn-tjZb94j15tCNA.png)

## Telling Faces apart

![Just bad TV](https://miro.medium.com/max/720/1*_GNyjR3JlPoS9grtIVmKFQ.gif){width=60% height=60%}

## Training Deep CNN

![](https://miro.medium.com/max/1035/1*n1R8VMyDRw3RNO3JULYBpQ.png){width=60% height=60%}

## Embedding

- `128`{.c} measurements of each face => embedding
  - Invented in 2015 by researchers at Google but many similar approaches exist
- Training a CNN to output face embeddings with a GPU
  - Takes about `24 hours`{.c} of continuous training to get good accuracy

## Sample Embedding

![](https://miro.medium.com/max/1627/1*6kMMqLt4UBCrN7HtqNHMKw.png)

# Conclusion

## Imagine an auction site

![Some valid items, some not](https://miro.medium.com/max/761/1*hOX0ejsh_0Bvk9FxZZ1c8Q.png)

## What we expect

![A little off reduces the accuracy](https://miro.medium.com/max/1071/1*m-QfVLt3TZuczJxNAuXxOg.png){width=70% height=70%}

## Can we fool the AI

![What do you think?](https://miro.medium.com/max/1215/1*6bUcVNpYPtZ5Nj-QDLSb6w.png)

## Which Algorithm II

### Algorithms Type II

- Supervised
- Unsupervised

### Results Type II

- Regression
- Classification

## Classification

![Green is ok, Red is bad](https://miro.medium.com/max/892/1*ZbIJhQZyCj1G96rgtID_vw.png){width=50% height=50%}

## A little nudge

![Move the red to the green](https://miro.medium.com/max/917/1*5cBIiAr0ex0mVDDI8eU1eQ.png){width=50% height=50%}

## Hacked Images

![Invisible to the human eye](https://miro.medium.com/max/1600/1*r4LpJUjIqXPtH3r6cMsgAg.png)

## What can AI do

- Regression
- Classification

What about other problems?

## 3 Card Monte

![I am not sure if AI can solve this](https://media0.giphy.com/media/UW9MtSTaXLXyw/200w.webp)

## Essay

- 1^st^ sentence from essay about
  - Addressing technology’s impact on humans’ ability to think for themselves

> "Invention for precincts has not, and presumably never will be undeniable in the extent to which we inspect the reprover."

<https://www.vice.com/en_us/article/pa7dj9/flawed-algorithms-are-grading-millions-of-students-essays>

## Criminal risk assessment algorithms

- Take in the details of a defendant’s profile
  - Return a recidivism score
    - a single number estimating the likelihood that he or she will reoffend
- Whats the issue with this?

<https://www.technologyreview.com/s/612775/algorithms-criminal-justice-ai>

## The end

![XKCD](https://miro.medium.com/max/267/1*wUZiI2Mg2cncuMWWXIiBgQ.png)

# Others

## Text Processing

## Parsing, Stemming, Lemmatization

- Tokenization: Split text into words
- Stemming: Find word stems
  - stating => state, reference => refer
- Lemmatization: Find base form of words

## Stop words

## Guess the next letter

> Robert Cohn was once middleweight boxi

## Recurrent Neural Network

![Past words matter](https://miro.medium.com/max/860/1*dcdVATcm0yJQxr4jGG5bFA.png)

## Speech Procesing

Speech = Text Processing + Acoustic model

## Reinforced Learning

![](https://miro.medium.com/max/478/1*HvoLc50Dpq1ESKuejhICHg.png)
