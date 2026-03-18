# Developer Tutorial
This section goes through step-by-step tutorials on how to build on top of MyFavoriteAlbums.

## Implementing Your Own Dataset  
MyFavoriteAlbums uses .csv (comma-separated values) files for its data. Create a .csv by exporting it from a spreadsheet application such as Excel.

### Creating a .csv File

1. Open Excel and create a blank workbook.  
2. Type Year in cell A1. Then fill in B1 through H1 with Ranking, Album, Artist, Rating, Vinyl, EP, Live, respectively.  
   ![taskcsv1.png](/images/taskcsv1.png)  
3. Complete the information for your own albums.  
   ![taskcsv2.png](/images/taskcsv2.png) 
4. Click on **File** \> **Export** \> **Change File Type** \> **CSV (Comma delimited)**  
5. Click **Save As** and save it somewhere convenient on your computer.

When opened in a text editor, the .csv file formatting should look something like this:  
![taskcsv3.png](/images/taskcsv3.png)

> **Important** Put quotation marks around artists and albums with commas in their names. 

### Importing a .csv File

1. Open RStudio and MyFavoriteAlbums’ **app\_ui.R** file  
2. Move your .csv file into the **data** folder.  
* If your .csv file is named **album-rankings.csv** delete the original file and skip the third step.  
3. Change the highlighted section of line 8’s   
   album\_data \<- read.csv("album-rankings.csv") to the name of your .csv file

> **Important** Due to the slider being hardcoded, change the beginning and end dates in **app\_ui.R** to fit with the new data.

---

## Implementing Your Own Features  
Currently, there are a number of features on the MyFavoriteAlbums application. Alongside creating a .R file for your feature, sections in app\_ui.R and app\_server.R must be added in order to display UI elements.  
### Implementing a New Feature

1. Create a new R file and write a function.  
2. Type Source(“\<yourfilename\>.R”)in the **app.R** file.  
3. Create output HTML and event logic in the **app\_server.R** file.  
4. Fill out the UI elements you want for your function in the **app\_ui.R** file using the tabPanel function.

Example:  
Creating a “Vinyl Owned” function.

1. Create an R file named **vinyl\_owned.R** and write the following code:  
```R Console
   \#Find top-rated albums that the person does own on vinyl  
   vinyl\_owned \<- function(vinyl\_owned\_rating.var){  
     owned \<- select(filter(album\_data\[order(-album\_data$Rating),\], Rating \>= as.numeric(vinyl\_owned\_rating.var), Vinyl \=="v"), Album, Year, Rating)  
   }  
   vinyl\_owned(10)  
```
2. Type the following in the **app.R** file.  
```R Console 
Source(“vinyl\_owned.R”)
``` 
3. Create the following HTML and event logic in the **app\_server.R** file.  
```R Console
   \# Seventh tab \- Vinyl Owned  
     output$text7 \<- renderUI({  
       HTML("\<h2\>Top-Rated Albums Owned on Vinyl\</h2\>\<br\>")  
     })  
     
     observeEvent(input$action\_button4,{  
       output$vinyl\_owned\_table \<- renderTable({  
         return(vinyl\_owned(input$vinyl\_rating))  
       })  
     })  
```
4. Use tabPanel function to create the UI elements for vinyl\_owned.R  
``` R Console
   tabPanel("Vinyl Owned",  
                    htmlOutput("text7"),  
                    selectInput("vinyl\_rating", "Select which albums to display:",  
                                c("Only 10 ratings" \= 10, "9 and higher" \= 9, "8 and higher" \= 8, "7 and higher" \= 7)),  
                    actionButton("action\_button4", label \= "Submit"),  
                    tableOutput("vinyl\_owned\_table"))
```
> For more features from the installed packages visit the [Developer FAQs](#dev-frequently-asked-questions-faqs) page for more resources

---

## Publishing Your Own MyFavoriteAlbums Website  
The easiest way to publish MyFavoriteAlbums onto a website is using ShinyApps. By installing the rsconnect and shiny package onto rstudio, you are able to connect MyFavoriteAlbums to ShinyApps. 

1. Create an account on [shinyapps.io](https://www.shinyapps.io/auth/oauth/signup)  
2. Click **Account** \> **Token** \> **Show** \> **Show Secret** to find a copyable text in this format:  
```
   rsconnect::setAccountInfo(name='\<yourname\>',  
   			  token='\<yourtoken\>',
			  	  secret='\<SECRET\>')
```
3. Copy and paste this text and run it into your R console in RStudio. This command links your shinyapps account to RStudio.  
4. In **app.R,** click **Publish** on the top right of RStudio’s text editor to publish MyFavoriteAlbums.  
* RStudio will ask what files from your directory you would like to publish, what your website title is, and to which shinyapps account to publish to. **Choose your desired publications**.   
5. Click **Publish**.
