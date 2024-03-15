

# Hierarchical Latent Variable Models for Neural Data Analysis
Sha lei: [s1lei@ucsd.edu](mailto:s1lei@ucsd.edu), Yutian Shi: [yus029@ucsd.edu](mailto:yus029@ucsd.edu), Courtney Cheung: [c6cheung@ucsd.edu](mailto:c6cheung@ucsd.edu), Shuyu Wang: [shw043@ucsd.edu](mailto:shw043@ucsd.edu)<br>
Mentor: Mikio Aoi [maoi@ucsd.edu](mailto:maoi@ucsd.edu)
        
Full Report:
<a href="https://github.com/courtneyacheung/Hierarchical-Latent-Variable-Models-for-Neural-Data-Analysis">Click Here </a>
<br>
GitHub code: 
<a href="https://github.com/courtneyacheung/Hierarchical-Latent-Variable-Models-for-Neural-Data-Analysis">Click Here </a>
<br>

## Introduction
The work on neural spike sorting has evolved substantially, emerging after new techniques that allow monitoring hundreds of neurons at the same time in a sub-millisecond. Nevertheless, due to the large amount of data that needs tobe processed, new algorithms that could handle the vast neural data while filtering useful parameters are mandatory. Our approach seeks to innovate by integrating these historical strengths while mitigating their weaknesses when performing the dimensional-reduction task, aiming for better capture of the dynamic of neural trajectories in the neural population activity.

We want to build a model that makes use of the advantages of GPFA and EM algorithms – namely, that GPFA works well with temporal data and that the EM algorithm is efficient for factor analysis, where multiple maximums need to be identified. Because Gaussian distributions produce positive and negative draws, a more appropriate modification to GPFA will use a Poisson distribution to reflect the true non-negative support of the discontinuous spike data. We would also like apply pCCA to two distinct brain regions in order to explore whether there is a relationship between neural activity in those regions during decision making tasks.

## Hierarchical Latent Variable Model Pipeline

### Data

The International Brain Laboratory used neuropixel probes to record neural activity from various mice brain areas during a decision-making task.

<div style="text-align: center;">
        <img src="./images/IBL dataset.jpg" style="width: 300px; height: 255px;" alt="Alt text">
</div>
<br>
Mice use a wheel to move a visual stimulus to the center of the screen, with varying probabilities of stimulus presentation on the left or right side. 

<div style="text-align: center;">
        <img src="./images/experiment.jpg" style="width: 300px; height: 255px;" alt="Alt text">
</div>
<br>

<div style="text-align: center;">
        <img src="./images/pipeline_eda.jpg" alt="Alt text">
</div >

*insert eda graphs*

<body>

<span style='font-size:100px;text-align: center' >&#8595;</span>

</body>

### Variational Gaussian Process Factor Analysis (vLGP)
Here, we learn the first layer of latent variables for each brain region. This model is a modifcation of Gaussian Process Factor Analysis (GPFA) using the Poisson Distribution as well as Variational Inference. 

<a href="https://arxiv.org/pdf/1604.03053.pdf">Learn about vLGP </a>
<br>
<a href="https://journals.physiology.org/doi/full/10.1152/jn.90941.2008?rfr_dat=cr_pub++0pubmed&url_ver=Z39.88-2003&rfr_id=ori%3Arid%3Acrossref.org">Learn about GPFA </a>
<br>
<a href="https://gregorygundersen.com/blog/2021/04/16/variational-inference/">Learn about Variational Inference </a>
<br>
<br>

#### Neural Trajectories of Superior Colliculus Deep Gray Layer:
<p align="center">
  <iframe src='./images/SCdg_train_trajectories_plot.html' width=938 height=565 frameBorder=0></iframe>
</p> 

#### Neural Trajectories of Superior Colliculus Intermediate White Layer:
<p align="center">
  <iframe src='./images/SCiw_train_trajectories_plot.html' width=938 height=565 frameBorder=0></iframe>
</p>

<body>

<span style='font-size:100px' >&#8595;</span>

</body>

### Probabilistic Canonical Correlation Analysis
After fitting our data to the vLGP model, we would explore multi-region analysis to examine variability shared between regions. This will give us insight into how activity in brain regions may be correlated versus distinct during a given task. For this analysis, we use Probabilistic Canonical Correlation (pCCA). 
<br>
<a href="https://gregorygundersen.com/blog/2018/09/10/pcca/">Learn about pCCA </a>
<br>

## Conclusion
From the two regions’ neural trajectories generated from the vLGP, there are clear separa- tions between wheels turning right and wheels turning left in the brain regions Superior Colliculus Deep Gray Layer and Intermediate White Layer, which means that there are different neural activity patterns under left and right direction conditions. However, we cannot make a conclusion about whether one region is driven by another when both are activated.

Increase in the number of latent variables in pCCA model leads to smaller RMSE be- tween the actual latent variable and estimated latent variable from the two regions, which conforms to the rules that with more latent variables, the model captures the complexity of the latent variable better.

*insert graph*

For future research, we would like to explore the correlation between regions in more depth by reconstructing the data based on the learned latent variables produced by pCCA. Further research could also include investigating whether there is causation between neural activity in the Superior Colliculus Deep Gray Layer and Intermediate White Layer.


