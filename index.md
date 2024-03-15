

# Hierarchical Latent Variable Models for Neural Data Analysis
Sha lei: [s1lei@ucsd.edu](mailto:s1lei@ucsd.edu), Yutian Shi: [yus029@ucsd.edu](mailto:yus029@ucsd.edu), Courtney Cheung: [c6cheung@ucsd.edu](mailto:c6cheung@ucsd.edu), Shuyu Wang: [shw043@ucsd.edu](mailto:shw043@ucsd.edu)<br>
Mentor: Mikio Aoi [maoi@ucsd.edu](mailto:maoi@ucsd.edu)
        
GitHub code: 
<a href="https://github.com/courtneyacheung/Hierarchical-Latent-Variable-Models-for-Neural-Data-Analysis">Click Here </a>
<br>

## Introduction
The work on neural spike sorting has evolved substantially, emerging after new techniques that allow monitoring hundreds of neurons at the same time in a sub-millisecond. Nevertheless, due to the large amount of data that needs tobe processed, new algorithms that could handle the vast neural data while filtering useful parameters are mandatory. Our approach seeks to innovate by integrating these historical strengths while mitigating their weaknesses when performing the dimensional-reduction task, aiming for better capture of the dynamic of neural trajectories in the neural population activity.



### Motivation

We want to build a model that makes use of the advantages of GPFA and EM algorithms – namely, that GPFA works well with temporal data and that the EM algorithm is efficient for factor analysis, where multiple maximums need to be identified. Because Gaussian distributions produce positive and negative draws, a more appropriate modification to GPFA will use a Poisson distribution to reflect the true non-negative support of the discontinuous spike data. We would also like apply pCCA to two distinct brain regions in order to explore whether there is a relationship between neural activity in those regions during decision making tasks.

## Data
<div style="text-align: center;">
        <img src="./images/IBL dataset.jpg" style="width: 300px; height: 255px;" alt="Alt text">
</div>
<br>

## EDA

<br>

## Hierarchical Latent Variable Model
### Data
<div style="text-align: center;">
        <img src="./images/Mice Brain Regions.jpg" alt="Alt text">
</div >

<style>
body {
  font-size: 20px;
}
</style>
<body>

<span style='font-size:100px; text-align: center;' >&#8595;</span>

</body>



### Gaussian Process Factor Analysis
   
### Variational Latent Gaussian Process

### Canonical Correlation Analysis

### Probailistic Canonical Correlation Analysis

<br>

## Procedure

<br>
    
## Results
<p align="center">
  <iframe src='./images/SCdg_train_trajectories_plot.html' width=938 height=565 frameBorder=0></iframe>
</p>    

<br>

## Discussion

<br><br><br>


