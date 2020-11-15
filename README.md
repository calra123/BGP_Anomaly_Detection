## BGP Anomaly Detection
Btech Project for College. BGP Anomaly Detection using unsupervised and supervised machine learning and detection of important features.

**Project Objectives**:

To be able to classify anomaly vs non-anomaly from the BGP update messages.

**Background Information**:

Border Gateway Protocol is the only External Gateway Protocol that is used to communicate routing and reachability information between Autonomous Systems (AS'es). BGP was made under
the assumption of trust, hence it has been compromised many times over the years. Some of the famous attacks are- Slammer, Nimda and Code Red I

These attacks have been used as the dataset to train the model. The training dataset consists of Slammer and Nimda. Code Red I has been used as the test dataset.

The main research paper I have worked on is the one cited below and tried to experiment with different features.
P. Batta, M. Singh, Z. Li, Q. Ding, and L. Trajkovi, “Evaluation of support vector
machine kernels fordetecting network anomalies,” IEEE International Symposium
on Circuits and Systems (ISCAS), Florence, 2018, pp. 1–4, 2018.

The main difference between their results and mine are, they concluded that the data was linearly separable but for me the Quadratic kernel gives the best accuracy.

**Steps to Run**

Steps to use or contribute towards this project:
* Need to have jupyter lab or run jupyter notebooks.
* Run the jupyter notebook named `svm_analysis_dataset1.ipynb`

The model is trained 3 times for different features - All 38 features, some selected features and Top 5 features based on their Pearson's correlation coefficient value.
In total it is being trained 12 times for each kernel as well- Linear, Quadratic, Cubic and RBF.

Some interesting observations-
The ROC curve for Cubic and RBF are almost identical.

I haven't made the whole training and analysis part into a function, so a part of the code needs to be commented out to train on different features dataset. 

Some things I overlooked-
* I used Karl Pearson's correlation coefficient to check whether the data point is an anomaly or not. To be able to use Pearson's, the underlying assumption is that data is normally
distributed. I didn't perform a test for normality.

Note: Please open an issue or comment if you have any doubts/queries.
