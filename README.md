### The Data:

Data colleted through [Kaggle](https://www.kaggle.com/datasets/jillanisofttech/lung-cancer-detection)

It has many variables:
 - GENDER : What gender the person is
 - AGE : The age of the person
 - SMOKING : If the person smokes or not
 - YELLOW_FINGERS : If the person presents yellowed fingers
 - ANXIETY : If the person has anxiety
 - PEER_PRESSURE : If the person is having a psychological pressure from other people
 - CHRONIC DISEASE : If the person has a chronic disease
 - FATIGUE : If the person presents fatigue
 - ALLERGY : if the person has any allergy
 - WHEEZING : If the person presents wheezing (acute sound while coughing)
 - ALCOHOL CONSUMING : If the person consumes alcohol
 - COUGHING : If the person has coughing
 - SHORTNESS OF BREATH : If the person has shortness of breath
 - SWALLOWING DIFFICULTY : If the person has swallowing difficulty
 - CHEST PAIN : If the person has chest pain
 - LUNG_CANCER : If the person has lung cancer
 
### Objective
Initially, I ahd the objective of develop the descriptive and exploratory analysis as I often do but now including the risk analysis. But, as I'll explain later, the data showed some problems, but first, let's have a look at initial analysis:

### Univariate
Here is a histogram grid to show the distribution of data inside our dataset:

![Histogram](Images/histograms.png 'Histogram')

 - The distribution of age is mostly between 45-80 years
 - Age is the only variable that is not a binary
 
![age](Images/age_hist.png 'Age Histogram')

 - Almost all of the variables have a balanced distribution
 - Fatigue and shortness of breath have most of their values as the number 2 (which means they have those symptoms)
 - Swallowing difficulty and is the only variable where most of the patients did not have that symptom

All the variables are categorical, except for Age, and are shown as 1 and 2.

There is not much more to talk about here.

### Bivariate
For the bivariate analysis I got stuck with only the correlation matrix below. I will explain why after some points that I saw within this matrix:

![Corerlation Matrix](Images/corr_matrix.png 'Corerlation Matrix')

Looking at the output LUNG_CANCER:
 - Lung cancer has a low correlation with smoking - This is a false correlation and it is probably being influenced by a third variable and needs more investigation
 - Yellow fingers is linked with smoking, but here it is not correlated, this is another false correlation
 - Anxiety a can cause Swallowing difficulty, shortness of breath, coughing and chest pain, that is why they are all correlated within the matrix. Those symptoms can also be linked to Lung Cancer due to its complications
 - Other chronic dieses like asthma, pulmonary fibrosis and other complications can help the development of lung cancer
 - Lung cancer influence the lungs directly, that is why fatigue has a high correlation
 - Allergies can have symptoms similar to lung cancer
 - Wheezing is generated when your airways are partially blocked. This blockage can be linked to allergies, mucus, inflamation or bronchitis
 - The consumption of alcohol is linked to a diverse number of complications and, some [studies](https://cancer.ca/en/cancer-information/reduce-your-risk/limit-alcohol/some-sobering-facts-about-alcohol-and-cancer-risk#:~:text=Drinking%20alcohol%20raises%20your%20risk,your%20risk%20of%20developing%20cancer.) says that it can be linked to cancer
 - As it affects the lungs, it is strange that the correlation of lung cancer and shortness of breath is low, but, this shortness can be caused by other variables, or the patients did not have this symptom
 - Lung cancer can reduce the strength of the muscles on your neck, creating difficulties in swallowing
 - It can also cause all levels of chest pain, depending on the development of the cancer
 
Some other correlations worth mentioning:
 - Anxiety and alcohol have a negative but high correlation. This can be due to the patients using alcohol to relieve stress/anxiety
 - Anxiety can also be linked to yellow fingers, being the highest of all correlations. As yellow fingers are created by smoking, those people are problably smoking to relieve anxiety, so the more they smoke, more yellow their fingers get, and as they are smoking to relive anxiety, the higher the anxiety, the more they smoke and more yellow the finger
 - Fatigue can also create shortness of breath
 - Smoking has a strangely low correlation with the other variables. Hard to explain, but this can have a plethora of explanations, one being they lied about smoking
 
Here a big problem with the data was found:
  - Smoking and Lung Cancer has a low correlation.
  - Yellow Fingers and Lung Cancer has a high correlation.
  
#### Why this is strange?
Yellow fingers is a symptom created by smoking. The toxins within the cigarette and the heat produced with the burn can yellow the fingers of the user. So, yellow fingers and smoking are directly linked. Meaning that the correlation within smoking and Lung Cancer is a really false correlation.

This shows how unreliable the data is.

Another clue to this is the proportion between people that has Lung Cancer and that don't have. The data shows that 87% of the patients has the disease. This don't represent the real proportions in the world population and can influence all the results within the analysis.

### Results
This data is not reliable, the proportion of patients that has Lung Cancer and the false correlations within the analysis make the data unpredictable and unreliable.

It would be better to seach for another dataset that has more patients and can represent more the real population. This would also increase the reliability of all the parameters measured.