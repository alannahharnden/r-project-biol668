# R Project - BIOL668
## Description
This is a completed R project for the BIOL 668 course taught by DSK at San Diego State.
- Required files:
  - RTestData-1.txt
  - grassland_data.zip (source: https://kembellab.ca/r-workshop/)

## Instructions (Part 1)
Download the necessary files, as included in this repository.


Utilize RTestData-1.txt for the exercises within the notebook titled 'Part 1,' and perform a variety of built-in R statistical tests on samples of the abundance of various bacteria from the oral cavity.

### Part A: Univariate Statistics with R

Begin by reading in this dataset. It's important that you use the title of the data, rather than a path specific to your computer, as that path is not universally available to other devices, i.e., anyone else you may share your code with.
```
data = read.table("RTestData-1.txt", header=TRUE)
data
```
You will follow by running normality checks and transformation of your bacterial data. Visualize your data with basic functions, e.g., ``hist()`` and ``qqnorm``, and normalize it with ``sqrt()``.

Perform one-way ANOVA tests, boxplots, and correlation analyses to summarize your data, its means, and linear correlation.

Finally, complete linear regressions, using ``lm()``, ``plot()``, and ``abline()``, for strep vs. deepest, and fuso vs. deepest. Use the following code as a guide:

```
x_vs_y <- lm(x ~ data$y)
plot(strep ~ data$y)
abline(x_vs_y)
```
### Part B: Using Ggplot to Make Pretty Graphs

To begin, install the required `` ggplot2 `` package. This is commented out in the provided notebook so that when you share yours with someone else, they can run the installation once and not have it re-run every time they execute their code. Follow by loading in the library.
You can then use ggplot() and interior parameters to design your graphs.
- For additional information, you may find the following `` ggplot2 `` tutorial useful: https://www.tutorialspoint.com/ggplot2/index.htm 


### Part C: Vegan Analysis 

Install the `` vegan `` package and load it in via ``library()``. This contains all sorts of tools for community ecology analysis. 

Since we only want to focus on the bacterial abundance variables within our initial dataset, it's recommended to make a new dataframe from that subset of data, and this can be done easily:

```
data2=data[2:6]
data2
```

Forward, you should utilize the general ``vegan`` tutorial, https://peat-clark.github.io/BIO381/veganTutorial.html, to calculate Shannon's index for measuring alpha diversity, generate Bray-Curtis dissimilarity matrix for assessing beta-diversity, and produce a ``rarecurve`` plot.

``rarefy`` may give you trouble in preparing data for rarecurve ploting, since the abundances are decimal form. Use ``round()`` to create whole integers that the function can work with. 

```
data2 = round(data2)
rare_data = rarefy(data2, rare_minimum)
rarecurve(data2, col = "purple")
```

Next, employ some multidimensional scaling (MDS) methods for elucidating the bacterial samples' relationships, based on dissimilarity, and producing a plot in multidimensional space. The following link will guide you through performing MDS with Bray-curtis matrix, and detail how you can color the plot by statis and time, using the aforementioned ``ggplot2``: https://environmentalcomputing.net/graphics/multivariate-vis/mds/


## Instructions (Part 2)

For the provided Part 2 notebook, the grassland_data.zip file was used, alongside the tutorial at http://kembellab.ca/r-workshop/biodivR/SK_Biodiversity_R.html.



