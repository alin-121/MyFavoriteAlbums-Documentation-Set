# Developers  
This section describes what you should know when jumping into modifying MyFavoriteAlbums for your personal needs. Familiarity with coding is recommended.

---

## Current Features  
MyFavoriteAlbums currently has 7 tabs; each using different values of the dataset to display different statistics. These are:

* Home: Serves as the landing page and displays the number of albums in the dataset, the number of artists in the dataset, and the artist with the most albums.  
* Number One Albums: Shows the highest rated albums based on a user inputted year interval from the year of the oldest release to the newest release.  
* Top Albums by Year: Shows all albums based on the chosen year.  
* Artists’ Albums: Shows all albums of a chosen artist.  
* Favorite Artists: Shows the high rated artists based off of selected minimum albums  
* Artist Comparison: Shows a line graph displaying two artists’ album ratings over time  
* Vinyl: Shows unowned vinyls based off of ratings

> Familiarize yourself with these features when creating new ones. 

---

## R & RStudio and .csv Files  
MyFavoriteAlbums’ code is based in R due to its design for data analysis and statistical computing. This document will not go over the details of coding in R and the user should be familiar with or use MyFavoriteAlbums to familiarize themselves with R to change or create new features. 

To change datasets or add features, you need to have RStudio installed on your computer. Some additional package installations on RStudio will be:
```R Console
* install.packages(‘rsconnect’)  
* install.packages(‘shiny’)  
* install.packages(‘dplyr’)  
* install.packages(‘ggplot2’)
```

rsconnect is used for publishing MyFavoriteAlbums onto Shinyapps.io  
shiny is used for the UI of your Shinyapps.io site.  
dplyr is used for easy-to-use data manipulation of dataset.  
ggplot2 is used for data visualization such as graphs.

A comma-separated values (.csv) file is needed to change the dataset for MyFavoriteAlbums. The information you will need is displayed in the table below. 

| Year | Ranking | Album | Artist | Rating | Vinyl | EP | Live |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
|  |  |  |  |  |  |  |  |

Example: 

| Year | Ranking | Album | Artist | Rating | Vinyl | EP | Live |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| 2021 | 1 | Nurture | Porter Robinson | 10 | v |  |  |

> The EP and Live sections are left blank as it does not pertain to the album’s information. As such it will also be left blank in the csv file formatting.  
   
**Year,Ranking,Album,Artist,Rating,Vinyl,EP,Live**  
2021,1,Nurture,Porter Robinson,10,v,, 

---

## Shinyapps.io  
[Shinyapps.io](http://Shinyapps.io) is a web service that allows users to publish their code to a website for free. It is an easy and painless process. You will only need to create a shinyapps account and connect RStudio to the web service. 

MyFavoriteAlbums files  
MyFavoriteAlbums uses R to run the logic and UI of the website. You can access the files on the [MyFavoriteAlbums GitHub page](https://github.com/UW-Example-Student/MyFavoriteAlbums). 

There are three main R files in this repository: app.R, app\_server.R, and app\_ui.R. These allow for the connection between RStudio and shinyapp such as the UI on your shinyapps website, and the logic to create each tab. The other R files are used to provide logic for each feature.  
