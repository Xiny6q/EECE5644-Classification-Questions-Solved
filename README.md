Download link :https://programming.engineering/product/eece5644-classification-questions-solved/

# EECE5644-Classification-Questions-Solved
EECE5644 Classification Questions Solved
Question 1 (50%)

The probability density function (pdf) for a 2-dimensional real-valued random vector X is as follows: p(x) = P(L = 0)p(x|L = 0) + P(L = 1)p(x|L = 1). Here L is the true class label that indicates which class-label-conditioned pdf generates the data.

The class priors are P(L = 0) = 0.65 and P(L = 1) = 0.35. The class class-conditional pdfs are p(x|L = 0) = w1 g(x|m01, C01) + w2g(x|m02, C02) and p(x|L = 1) = g(x|m1, C1), where g(x|m, C) is a multivariate Gaussian probability density function with mean vector m and covariance matrix C. The parameters of the class-conditional Gaussian pdfs are: w1 = w2 = 1/2, and

m01 = [ 30 ] C01 = [ 20 01 ] m02 = [ 03 ] C02 = [ 10 02 ] m1 = [ 22 ] C1 = [ 10 01 ]

For numerical results requested below, generate 10000 samples according to this data distribu-tion, keep track of the true class labels for each sample. Save the data and use the same data set in all cases.

Part A: ERM classification using the knowledge of true data pdf:

1. Specify the minimum expected risk classification rule in the form of a likelihood-ratio test:

p(x|L=1) ? g, where the threshold g is a function of class priors and fixed (nonnegative) loss

p(x|L=0) >

values for each of the four cases D = i|L = j where D 2 0, 1 is the decision.

Implement this classifier and apply it on the 10K samples you generated. Vary the threshold g gradually from 0 to •, and for each value of the threshold estimate P(D = 1|L = 1; g) and P(D = 1|L = 0; g). Using these paired values, plot an approximation of the ROC curve of the minimum expected risk classifier. Note that at g = 0 The ROC curve should be at ( 11 ), and as g increases it should traverse towards ( 00 ). Due to the finite number of samples used to estimate probabilities, your ROC curve approximation should reach this destination value for a finite threshold value.

Determine the theoretically optimal threshold value that achieves minimum probability of er-ror, and on the ROC curve, superimpose (using a different color/shape marker) the operating point of this min-P(error) decision rule by evaluating its two confusion matrix entries needed for its ROC curve point. Estimate the minimum probability of error that is achievable for this data distribution using the dataset and this theoretically optimal threshold. In addition, by evaluating estimated P(error; g) = P(D = 1|L = 0; g)P(L = 0) + P(D = 0|L = 1; g)P(L = 1) values, determine empirically using the dataset a threshold value that minimizes this esti-mated P(error) value. How does your empirically determined g value that minimizes P(error) compare with the theoretically optimal threshold you compute from priors and loss values?

Part B: Repeat the same steps as in the previous two cases (draw ROC curve & find threshold that minimizes P(error)), but this time using a Fisher Linear Discriminant Analysis (LDA) based classifier. Using the 10K available samples and their labels, estimate the class conditional mean and covariance matrices using sample average estimators. From these estimates, determine the Fisher LDA projection weight vector (via the generalized eigendecomposition of within and between class scatter matrices): wLDA. For the classification rule wTLDAx compared to a threshold t, which

takes values from −• to •, plot the ROC curve. Identify the threshold at which the probability of error (based on sample count estimates) is minimized, and mark that operating point on the ROC curve estimate. Discuss how this LDA classifier performs relative to the previous two classifiers. Compare the P(error) achieved by LDA with that of the optimal design.

Note: When finding the Fisher LDA projection matrix, do not be concerned about the difference in the class priors. When determining the between-class and within-class scatter matrices, use equal weights for the class means and covariances, like we did in class. You could argue for a weighted approach, but in this case the model mismatch is a more serious issue to be concerned about.

Question 2 (50%)

A 3-dimensional random vector X takes values from a mixture of four Gaussians. One of these Gaussians represent the class-conditional pdf for class 1, and another Gaussian represents the class-conditional pdf for class 2. Class 3 data originates from a mixture of the remaining 2 Gaussian components with equal weights. For this setting where labels L 2 {1, 2, 3}, pick your own class-conditional pdfs p(x|L = j), j 2 {1, 2, 3} as described. Try to approximately set the distances between means of pairs of Gaussians to twice the average standard deviation of the Gaussian compoenents, so that there is some significant overlap between class-conditional pdfs. Set class priors to 0.3, 0.3, 0.4.

Part A: Minimum probability of error classification (0-1 loss, also referred to as Bayes Deci-sion rule or MAP classifier).

Generate 10000 samples from this data distribution and keep track of the true labels of each sample.

Specify the decision rule that achieves minimum probability of error (i.e., use 0-1 loss), implement this classifier with the true data distribution knowledge, classify the 10K samples and count the samples corresponding to each decision-label pair to empirically estimate the confusion matrix whose entries are P(D = i|L = j) for i, j 2 {1, 2, 3}.

Provide a visualization of the data (scatter-plot in 3-dimensional space), and for each sample indicate the true class label with a different marker shape (dot, circle, triangle, square) and whether it was correctly (green) or incorrectly (red) classified with a different marker color as indicated in parentheses.

Part B: Repeat the exercise for the ERM classification rule with the following loss matrices which respectively care 10 times or 100 times more about not making mistakes when L = 3:

L10 =

4

0

1

10

5

and L100 =

4

0

1

100

5

1

1

0

1

1

0

2

1

0

10

3

2

1

0

1003

(1)

Note that, the (i, j)th entry of the loss matrix indicates the loss incurred by deciding on class i when the true label is j. For this part, using the 10K samples, estimate the minimum expected risk that this optimal ERM classification rule will achieve. Present your results with visual and numerical reprentations. Briefly discuss interesting insights, if any.

