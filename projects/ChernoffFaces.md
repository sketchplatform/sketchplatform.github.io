---
layout: page
title: Chernoff Faces
subtitle: By Vincent Lee
---

This is just a test of uploading different file formats onto my webpage. 

### Chernoff Faces

Humans have built-in facial recognition in their brains. We are programmed to respond to facial features. Herman Chernoff, a statistician and physicist, came up with the idea of representing data with cartoon-like faces.

```{r}
library(aplpack)

crime.df <- read.csv("crimeRatesByState.csv")
str(crime.df)
```

Generate faces on the data. The first column will be the labels.
```{r}
faces(crime.df[,2:7])
```
Change to no color.
```{r}
faces(crime.df[,2:7],face.type=0)
```
Now add labels instead of the index numbers.

```{r}
faces(crime.df[,2:7], labels=crime.df$state)
```

The smile is not really appropriate for a negative statistic like burglary (unless you are the Joker in Batman). Add a vector of ones so that "smiling" will be neutralized.

Smiling is the sixth feature in the list of features used by the faces function. We will not use the first column of the data set for the faces function as it contains the labels, so we need to add a ones column at column number 7 to neutralize smiling.

```{r}
crime.nosmile <- cbind(crime.df[,1:6], rep(1, length(crime.df$state)), crime.df[,7])
faces(crime.nosmile[,2:8], labels=crime.nosmile$state)
```

What if we want to use a subset of the columns, just murder, burglary, and motor vehicle theft?

Make these assignments:
height of face=murder, width of face=burglary, and style of hair=motor vehicle theft.

Because the data size is less than the facial features, the data columns rotate. To control this, create a matrix with all constant values, then fill in the coluns we want to display as a facial feature with data.

```{r}
mat.to.plot <- matrix(1,nrow=nrow(crime.df),ncol=15) #all values are 1 (default)
rownames(mat.to.plot)<- crime.df$state
```
Now add the data at the column that corresponds to the facial feature we want.
```{r}
mat.to.plot[,1]<-crime.df[,2]
mat.to.plot[,2]<-crime.df[,5]
mat.to.plot[,9]<-crime.df[,7]

faces(mat.to.plot,face.type=0)
```

This type of plotting is best for identifying faces that "stand-out" from the rest rather than assessing one or two variables.

Now use the state_data.csv data set to produce some Chernoff faces. Start by using all of the data, with the state abbreviations as the labels. Then, pick a subset of the data and plot the faces for that subset.
```{r}
state <- read.csv("state_data.csv")
str(state)
#head(state)
#dim(state)
```
Generate faces on the data. The first column will be the labels.
```{r}
faces(state[,2:9])
```
No color.
```{r}
faces(state[,2:9],face.type=0)
```
Labels instead of the index numbers.
```{r}
faces(state[,2:9], labels=state$State)
```
The smile is not really appropriate for a negative statistic like MURDER so we add a vector of ones so that "smiling" will be neutralized.

Smiling is the sixth feature in the list of features used by the faces function. We will not use the first column of the data set for the faces function as it contains the labels, so we need to add a ones column at column number 7 to neutralize smiling.
```{r}
crime.nosmile2 <- cbind(state[,1:6], rep(1, length(state$State)), state[,7])
faces(crime.nosmile2[,2:8], labels=crime.nosmile2$State)
```
What if we want to use a subset of the columns say, just murder, illiteracy, and income?

Make these assignments:
height of face=murder, structure of face=illiteracy, and width of mouth=income.

Because the data size is less than the facial features, the data columns rotate. To control this, create a matrix with all constant values, then fill in the coluns we want to display as a facial feature with data.
```{r}
mat.to.plot2 <- matrix(1,nrow=nrow(state),ncol=15) #all values are 1 (default)
rownames(mat.to.plot2)<- state$state
```
Now add the data at the column that corresponds to the facial feature we want.
```{r}
mat.to.plot2[,1]<-state[,2]
mat.to.plot2[,3]<-state[,4]
mat.to.plot2[,5]<-state[,6]

faces(mat.to.plot2,face.type=0)
```

Next, try the NFC-OffenseData.csv and NFC-DefenseData.csv data sets. Add titles to the plots. What can you say about these team's offense and defense last year?
```{r}
NFC.off <- read.csv("NFC-OffenseData.csv")
str(NFC.off)
#head(NFC.off)
#dim(NFC.off)
faces(NFC.off[,2:9])
faces(NFC.off[,2:9], labels=NFC.off$Team)

#Those who perform offensively display longer distances and greater number of points.

mat.to.plot3 <- matrix(1,nrow=nrow(NFC.off),ncol=15) #all values are 1 (default)
rownames(mat.to.plot3)<- NFC.off$Team

mat.to.plot3[,5]<-NFC.off[,1]
mat.to.plot3[,6]<-NFC.off[,2]

faces(mat.to.plot3,face.type=0)
```

```{r}
NFC.def <- read.csv("NFC-DefenseData.csv")
str(NFC.def)
#head(NFC.def)
#dim(NFC.def)
faces(NFC.def[,2:9])
faces(NFC.def[,2:9], labels=NFC.def$Team)

#Those who perform well defensively display a large number of total yards and yards gained.

mat.to.plot4 <- matrix(1,nrow=nrow(NFC.def),ncol=15) #all values are 1 (default)
rownames(mat.to.plot4)<- NFC.def$Team

mat.to.plot4[,1]<-NFC.def[,7]
mat.to.plot4[,2]<-NFC.def[,8]

faces(mat.to.plot4,face.type=0)
```

### Conclusion

By looking at  some Chernoff faces you can identify how well did the players perform in their team's offense and defense last year. Apparently the teams with faces that look unique, excited, and grandiose perform better offensively and defensively. Compared to teams with faces that look small, sad, and insignificant perform worse in those categories.





