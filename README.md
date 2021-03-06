# Wine Quality -  Analysis
Author: [Joffrey Bienvenu](https://github.com/Joffreybvn)

Analysis and interpretation of a [red wine quality's dataframe](https://www.kaggle.com/uciml/red-wine-quality-cortez-et-al-2009).

### Objectives:
 - [x] Using Pandas for data manipulation.
 - [x] Using MatplotLib and/or Seaborn for plotting.
 - [x] Finding and understanding correlations between dataset's variables.

### Goals:
1. Determine **the criteria that influence the quality** of red wine by analysing the dataframe.
2. Find out **which are the best and worst** wines.

# Data analysis
The complete analysis and its details is avaibale on [Google collab](https://colab.research.google.com/drive/1VdehLoCJraz0GHCz8B6EmgoCrP33TVoc?usp=sharing), or directly in the [notebook of this repo](https://github.com/Joffreybvn/wine-quality-analysis/blob/master/wine_quality_analysis.ipynb).

## The target: the Quality

The quality index in the dataframe is obviously the target variable. A good quality means a good wine, while a bad quality means a bad wine. The following analysis tried to **understand and explain wich variables have influences on quality, how and how much ?**

### Variable distribution:
Fortunately, this dataset is quite clean. Same for the *quality*, which is quite well distributed:

**Skew:** 0.192 - **Kurtosis:** 0.340
![https://raw.githubusercontent.com/Joffreybvn/wine-quality-analysis/master/visualisations/quality.svg](https://raw.githubusercontent.com/Joffreybvn/wine-quality-analysis/master/visualisations/quality.svg)

## Correlations between variables

This heatmap shows the correlations bewteen variables, and was **used to investigate which kind of relations** variables have between them.

![https://raw.githubusercontent.com/Joffreybvn/wine-quality-analysis/master/visualisations/heatmap.svg](https://raw.githubusercontent.com/Joffreybvn/wine-quality-analysis/master/visualisations/heatmap.svg)

### Investigation order:
Some correlations are more interesting to investigate than others.

1. Investigate the 4 strongest correlations bewteen **quality** and *others variables**.
2. Investigate the strongest correlations **between these 4 variables**.
3. Gradually investigate the strongest correlations between theses 4 variables, and **the rest of the variables** (the presumably "*less*" important ones).

The complete investigation with the observations, can be found on [Google collab](https://colab.research.google.com/drive/1VdehLoCJraz0GHCz8B6EmgoCrP33TVoc?usp=sharing), or directly in the [notebook of this repo](https://github.com/Joffreybvn/wine-quality-analysis/blob/master/wine_quality_analysis.ipynb).

## Conclusion:

After investigating and understandng the nature of the correlations bewteen the *quality* and the *others variables*, I came to the following conclusion:

<p align="center">
  <img src="https://raw.githubusercontent.com/Joffreybvn/wine-quality-analysis/master/visualisations/wine.svg">
</p>

A good wine is a subtle mix between *Sulphates* and *Chlorides* on one hand, and *Sugar* and *Sulfur dioxide* on the other hand. In order to to balance the *Citric acid* with the *Fixed acidity*, and therefore get enough *alcohol* and *volatile acidity* in your wine, which are the main influence of the wine's quality.

## Explanations:

A wine is good when its **quality** is high. To have a higher quality, the wine needs:
- A higher *alcohol* concentration.
- A smaller *volatile acidity* concentration.

**A good wine is a wine with lot of alcohol and few volatile acidity.**

### How to increase *alcohol* concentration ?
The *alcohol* concentration can be increased thank to two variables:
1. When the wine has **less *Sulfur dioxide***. 
2. When the wine has **a smaller *density***, wich is directly influenced by the *residual sugar*.<br>
<img src="https://raw.githubusercontent.com/Joffreybvn/challenge-collecting-data/master/docs/arrow.svg" width="12"> Less *residual sugar* means less density, wich means *more alcohol* !

But the *density* is also **highly influenced by the *Fixed acidity***: **Less *fixed acidity* is better to have more alcohol** ! We'll see later how *fixed acidity** interact with the other variables.

### How to decrease the *volatile acidity* ?
The *volatile acidity* is mainly and directly influenced by **the *Citric acid* concentration**: More *citric acid* means less *volatile acidity*, which means a better wine.

The *citric acid* concentration can be increased thanks to a higher *Sulphates* concentration, and a higher *Chlorides** concentration. 

### The *Citric acid* & *Fixed acid* problem:
As we saw earlier, more *citric acid* means indirectly having a better wine. And less *fixed acidity* means indirectly having more alcohol, and so a better wine.

However, **increasing the *citric acid* concentration makes the *fixed acidity* concentration increasing too** ! Therefore, you can't blindly increase the *citric acid* because it will makes the wine having less *alcohol*. Or, your must compensate by reducing the *residual sugar* ans the *sulfur dioxide*. 

# Data interpretation: Is my wine good ?

To challenge the conclusion of the analysis, the top 5 best and worst wine can be found on [Google collab](https://colab.research.google.com/drive/1VdehLoCJraz0GHCz8B6EmgoCrP33TVoc?usp=sharing), or directly in the [notebook of this repo](https://render.githubusercontent.com/view/ipynb?commit=ca6f01cacde63e40d4c6d6c1d756f972c8bc284b&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f4a6f666672657962766e2f77696e652d7175616c6974792d616e616c797369732f636136663031636163646536336534306434633664366331643735366639373263386263323834622f77696e655f7175616c6974795f616e616c797369732e6970796e62&nwo=Joffreybvn%2Fwine-quality-analysis&path=wine_quality_analysis.ipynb&repository_id=297652114&repository_type=Repository#Five-better-wines).
