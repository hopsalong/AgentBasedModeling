1. Provide a written description of your selected household survey including the number of household and person observations as well as the variables in your source data.

For this project I continued my focus on Guniea. I decided to look specifically at the Boke region, which is where the Koundara prefecture (which I analyzed for the last project) is located. I downloaded my survey data from DHS and selected columns for education, age, gender, location, size and weights to be in my data frame. There are a total of 7912 household observations in guniea (1073 of which are in Boke), and 10874 persons observations. 

2. Provide a written description of your spatially located households at the adm0 level of your selected location, including how you located each household, generated the household structure including demographic attributes of persons, and the percent error calculated. If you faced computational issues at the adm0 level when attempting to pivot from households to persons, describe those limitations.

I used rpoint to randomly generate points based on the population raster's density. I then used slice_sample to take a random sample of the DHS data (specifically of the dataframe discussed above), and combined that with the random points to create an artifical household spatial dataframe. The weighted error for this was 0.0002060102, which is quite good. However, I sadly wasn't able to spatially locate my households on the adm0 level, because I kept running into an error that told me that R didn't have enough memory to complete the function. I tried many things to fix this problem, like allocating more memory space to R and doing the project on a cloud computing platform, but I wasn't able to get anything to work. This was disapointing, because I believe I would have gotten better results if I had been able to look at all of Guniea instead of just the 1073 household observations in Boke.



3. Provide a written description of your spatially located households at the adm1 or adm2 level of your selected location, again including how you located each household, generated the household structure including demographic attributes of persons, and the percent error calculated. Further analyze your synthetically generated households and persons with regard to percent error. Do you think this population is more or less accurate than the one generated at the adm0 level? What could you have done to improve your measures of accuracy?

I repeated the same process as above in order to create a random point graph with household data based on the population raster's density that was specific to Boke. The weighted error was .2536, which tells us that doing analytics on the adm0 level will give us better results than on the adm1 level.
![](rpoint_boke.PNG)

I then created density plots that show the size of the households in Boke (which is represented by the green line) and Guinea (which is represented by the yellow curve). 
weighted error = 0.0004734058

![](density1_2.PNG)

The first plot compares all of the households in Boke to all of the households in Guinea. The match is fairly good.

![](density2_2.PNG)

The second plot takes a random subsets of the households of Guinea and Boke equal to the number of households in Boke, and uses that as the comparison. The match is better here by a little bit.


4. When compared to a randomly generated synthetic population that describes the demographic attributes of households and persons, does yours more closely approximate reality? How is yours an improvement over a synthetic population that was generated in accordance with complete spatial randomness? Generate plots and incorporate results from your work as evidence in support of an argument that the synthetic population you generated is a good approximation of the reality that existed in your selected location at that given time.


Next I made heatplots to demonstrate the predictive power of the data. I selected the age, gender, education and size columns to focus on. I made heatmaps with raw data, scaled data, normalized data, and percentized data. 

![](raw2.png)

The raw data heatmap is mostly homogenous, the only variable that produces different combinations is age, which means that it could be a useful predictor. 

![](scale.png)

The scaled data heatmap is also fairly homogenous, but much less so than the raw data. This means that it has more predictive power.

![](normal2.png)

The normalized data is very interesting. There is some variability in size and a lot in age, but most notably there is a complete binary in gender. This is most likely because of the large gender gap in education in Guinea.

![](percent2.png)

The percentized data has the most variability, and the most predictive power out of all of the data processing techniques.


Next I conducted a multinomial regression and ranger random forest to predict education. I then produced Gain and ROC charts for each regression.

![](multireg_gain2.PNG)
![](multireg_roc2.PNG)

The above charts show the multinomial regression, which had an accuracy of .62. Both the Gain and ROC charts indicate that the model isn't a particularly strong predictor. 

![](rf_gain2.PNG)
![](rf_roc2.PNG)

The above charts show the random forest model, which had an accuracy of .663. Although the accuracy score is not significantly higher than that of the multinomial regression, the ROC charts show a dramatic improvement, telling us that there is a higher true positive vs false positive rate for the random forest. 


Finally, I created a neural net with keras and tensorflow in order to predict education. It had an accuracy of .699 which is slightly higher than the random forest I created in the previous stage of my analysis. You can see the confusion matrix produced below, which tells you what level of education (0, 1, 2, or 3) the model has predicted for each person, and the actual true level of education they have attained.

![](confmat.PNG)

Lastly, I produced a graph that shows the correlations between age, household size, and predicted education level. Size is not a very strong predictor, but age seems to do a fairly good job.
![](nn_graph.PNG)
