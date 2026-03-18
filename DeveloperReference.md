# References for Developers
FAQs, references for existing functions, and Shinyapps.io accounts. 

## Dev Frequently Asked Questions (FAQs)  
### How do I use R files?  
To use R files, you must download RStudio from the [RStudio download site](https://posit.co/download/rstudio-desktop/).  
Follow the instructions on the page and RStudio will be ready to use on your computer.

### Where do I get the R files for MyFavoriteAlbums?   
The files for MyFavoriteAlbums are published on its [GitHub page](https://github.com/UW-Example-Student/MyFavoriteAlbums).   
To download and use the files:

1. Click on the green **Code** button and download the zip file.   
2. Extract the zip file.  
3. Use RStudio to open and edit the R files.

### What functions can I use with the packages I have installed?

* ggplot: You can visit the ggplot [package index page](https://ggplot2.tidyverse.org/reference/index.html) to find all the functions.  
* shiny: You can visit the shiny [function reference page](https://shiny.posit.co/r/reference/shiny/latest/) to find all the functions.  
* dplyr: You can visit the dplyr [overview page](https://dplyr.tidyverse.org/) to find all the functions.

---

## MyFavoriteAlbums Existing Functions  
### home.R

* total\_album\_count  
  Inputs: N/A  
  Outputs: N/A  
  Function: Counts all albums in the .csv file and prints out a string with the amount  
    
  ![reftotal_album_count.png](/images/reftotal_album_count.png)
* total\_band\_count  
  Inputs: N/A  
  Outputs: Integer of bands in the .csv file  
  Function: Prints the number of bands in the data  
    
  ![reftotal_band_count.png](/images/reftotal_band_count.png)  
* most\_pop\_artist  
  Inputs: N/A  
  Outputs: N/A  
  Function: Prints the artist with the most albums in the data  
    
  ![refmost_pop_artist.png](/images/refmost_pop_artist.png)

### number\_one\_albums.R

* number\_one\_album  
  Inputs: startyear, endyear  
  Outputs: List of \#1 album within the year range  
  Function: Lists out the \#1 album between the startyear and the endyear along with their release year, album name, and artist name.  
  ![refnumber_one_albums.png](/images/refnumber_one_albums.png)


### albums\_by\_year.R

* year\_albums  
  Inputs: year  
  Outputs: Ranking of albums in selected year  
  Function: Lists out the ranking of albums in user inputted year

	![refalbums_by_year.png](/images/refalbums_by_year.png)

### albums\_by\_band.R

* albums\_by\_bands  
  Inputs: band  
  Outputs: List of all albums from input band  
  Function: Filters out the album data by band name.  
  ![refalbum_by_bands.png](/images/refalbum_by_bands.png)
    
* band\_mean\_rating  
  Inputs: band  
  Outputs: N/A  
  Function: Filters out the album data by band name, averages the band ratings, then prints the average ratings.  
  ![refband_mean_rating.png](/images/refband_mean_rating.png)
    
* band\_album\_count  
  Inputs: band  
  Outputs: N/A  
  Function: Filters out the album data by band name, counts the number of albums, prints the album count  
  ![refband_album_count.png](/images/refband_album_count.png)

### fav\_bands.R

* favorite\_bands  
  Inputs: min\_albums, live\_ep  
  Outputs: Ranking of artists displayed with their average rating and number of albums  
  Function: Checks if live\_ep is true, then filters artists based off of input min\_albums while ranking them by average rating across their albums.

	![reffavorite_bands.png](/images/reffavorite_bands.png) 

### compare\_bands.R

* band\_album\_comparison\_chart  
  Inputs: artist1, artist2  
  Outputs: line graph using the ggplot package  
  Function: Filters the data to only albums by the input artists. Then plots all the album ratings over the years using ggplot.  
  ![refband_album_comparison1.png](/images/refband_album_comparison1.png)
  ![refband_album_comparison2.png](/images/refband_album_comparison2.png)

### vinyl.R

* missing\_vinyl  
  Inputs: missing\_vinyl\_rating  
  Outputs: List of albums filtered by input   
  Function: Filters data by input missing\_vinyl\_rating and whether vinyl is owned (from .csv file data).  
  ![refmissing_vinyl.png](/images/refmissing_vinyl.png)

### app.R  
Allows use of Shinyapps on RStudio. This file instantiates the needed libraries and all the R files in order to connect RStudio to Shinyapps.

### app\_server.R

* server  
  Inputs: input, output  
  Output: HTML, tables, text, plot  
  Function: Instantiates UI elements and logic between R files and changes based off of the input variable. 

### app\_ui.R  
Creates the UI for the MyFavoriteAlbums website. Tabs are created using shinyapps functions while also instantiating UI elements such as text, sliders, etc. 

---

## Shinyapps.io account  
[Shinyapps.io](http://Shinyapps.io) has their own user documentation under the domain:

[https://docs.posit.co/shinyapps.io/guide/](https://docs.posit.co/shinyapps.io/guide/)

> This site is a helpful resource for those who need assistance with how shinyapps works and all the account-side functions it has.

