# capstone-skin-cancer-detection

## Abstract
  
  Early in the Data Science Immersive course, Farshad Nasiri, the DC local lead instructor, was filling me in on some of the applications of data science in modern medicine.  He explained to me why it's unwise for a medical student to choose the field of radiology, as computers are now better equipped to do the job than humans are, regardless of experience.  New imagery techniques can detect shades of color with significantly better precision than a human eye can.  Also, machines can be trained with millions of images very quickly, while a doctor with decades of experience is likely to have only seen thousands of images in their career.<br>
  
  This sparked an idea for me, to potentially create an application that can make a map of someone's skin.  All current moles/marks/lesions etc. would be measured and recorded.  New growths and changes in current ones can be recorded over time and compared with millions of known cases and anything troublesome would be classified as 'potentially dangerous.'  The user would then be provided with a list of local dermatologists who accept their insurance.  An actual doctor would take it from there.<br>
  
  Initially, this seemed like a very feasible product to develop.  I searched to see if anything like this existed, and found 7 existing applications on the market that more or less do what I described above.  Scientists have actually been developing machines "to distinguish dangerous skin lesions from benign ones" for some time now, and a computer was able to detect malignant melanomas with 95% accuracy compared to 86.6% from dermatoligists of varied experience.[1]  As the weeks went on in the course, and I struggled at times with things like Logistic Regression and NLP, I added this idea to my 'out of scope' list, and mostly forgot about it.  The idea wasn't new and seemed too advanced anyway.<br>
  
  In searching for a capstone, this idea floated around again, and, after some initial doubt, I'm inspired to complete it.  Some of this inspiration came from seeing a past capstone in the General Assembly gallery.  GA graduate Samuel Bozek (SF) did their project using neural networks with a binary classification to determine whether a painting was done by French Impressionist Claude Monet or a different artist. [2]<br>
    
### Step 1 - Define the Problem
  
  "Skin cancer is the most common form of cancer, globally accounting for at least 40% of cases."[3][4][5]  It's also the most treatable cancer, especially when detected early.  "In the United States (skin cancers) were the cause of less than 0.1% of all cancer deaths."[3][6]<br>
  
  The goal of this project is to use convolutional neural networks (CNNs) and the tools from the Keras library to classify whether an image of a Nevus, lesion, or other skin anomaly is potentially dangerous or not.  As it stands now, performing a binary classification (harmful/not) may be the best route to take.  It's possible that the model will be used to differentiate between different types of diseases (melanoma, basal-cell skin cancer (BCC), squamous-cell skin cancer (SCC)).[3][6]  **In the next two days, I will need to make a final decision on what type of classification model to run.**
  
  Potential issues and obstacles I expect to face are the following:<br>
    1. I am not, by any stretch, a subject matter expert.  My instructors are not either.  I will spend the beginning of this week researching and learning more about types of skin cancer.<br>
    2. Being a new data scientist, I have very little experience with CNNs, image recognition, etc.<br>
    3. My machine may not be able to handle the size of the dataset.  I plan to use filters, convolution, and borders to compress the images.  I will likely be able to over come this through use of Amazon Web Services (AWS) to carry the computational load of modeling.<br>
    4. Having back up data and gathering further testing data could be difficult.<br>
      
### Step 2 - Gather data

  For now, all data is gathered from the “ISIC: Skin Lesion Analysis Towards Melanoma Detection“ grand challenge, 2018.[6]  The master set from this challenge contains about 11500 images, pre-split at about an 87/13 train/test ratio.  Additional data for testing can potentially be gathered by scraping images, or from other smaller public datasets. 
  
### Step 3 - Explore data & 
### Step 4 - Model with data

  Data has not been explored yet.  Some guidance on how to approach this problem will be taken from General Assembly DSI lessons 10.04/5, and an in-class codealong which used the Modified National Institute of Standards and Technology (MNIST) database to identify hand-written digits with CNNs. 
   
  Data prep will likely include convolutional fitering to compress the image and flattening to run images through a CNN.
  
### Step 5 - Evaluate model
  
  Evaluation of this model will be conducted using classification metrics to include: confusion matrix, accuracy, specificity, sensitivity, precision, misclassification, area under curve.  Efforts will be made to reduce type 2 errors, as this project  will be a simulation of medical testing and false negatives are far more consequential than other 'misses'.  
  
  I'm hoping to get guidance from instructors in deciding what kind of scores will constitute a 'good model.'  I'd consider anything that compares to, or outperforms human doctors to be sucessful.  According to the Guardian article referenced above, this number could be as high as 86.6%.[1]  Another experiment, conducted at Stanford University, using the ISIC dataset I'll be using for my model claimed accuracy numbers of around 72% for their CNN and around 66% for their dermatologists on the same set.[7]
  
### Step 6 - Answer problem

  Tentatively, by Wednesday, October 17th, visualizations and an answer will be ready to be formulated and compiled for presentation.
  

[1] https://www.theguardian.com/society/2018/may/29/skin-cancer-computer-learns-to-detect-skin-cancer-more-accurately-than-a-doctor <br>
[2] 'Show me the Monet' http://res.cloudinary.com/general-assembly-profiles/image/upload/v1467305840/jeypsq559sd5ak79ayc0.pdf <br>
[3] https://en.wikipedia.org/wiki/Skin_cancer <br>
[4] Cakir, BÖ; Adamson, P; Cingi, C (November 2012). "Epidemiology and economic burden of nonmelanoma skin cancer". Facial plastic surgery clinics of North America. 20 (4): 419–22. doi:10.1016/j.fsc.2012.07.004. PMID 23084294. <br>
[5] Jou, PC; Feldman, RJ; Tomecki, KJ (June 2012). "UV protection and sunscreens: what to tell patients". Cleveland Clinic journal of medicine. 79 (6): 427–36. doi:10.3949/ccjm.79a.11110. PMID 22660875. <br>
[6] "Skin Cancer Treatment (PDQ®)". NCI. 25 October 2013. <br>
[7] Letter | Published: 25 January 2017 <br>
Dermatologist-level classification of skin cancer with deep neural networks <br>
Andre Esteva, Brett Kuprel, Roberto A. Novoa, Justin Ko, Susan M. Swetter, Helen M. Blau & Sebastian Thrun <br>
available at: https://www.nature.com/articles/nature21056
