Developing Data Products: Course Project
========================================================
 
date: 18.10.2019
autosize: true
width: 1600
height: 900

Introduction and Overview
========================================================

This presentation and the associated Shiny app conclude the Coursera course: Developing Data products. 

Included in this project are:

- this presentation, providing an overview, code examples and links
- a Shiny app hosted on shinyapp.io
- the corresponding source code hosted via github

Please see the Appendix for links to the files.

UI Example
========================================================

![Caption](ui_example.png)

Example Code with server.ui calculation
========================================================


```r
# create linear model
  
  output$predict <- renderPrint({
    diamonds_sub <-
      subset(
        diamonds,
        cut == input$cut &
          color == input$color &
          clarity == input$clarity
      )
    
    fit <- lm(price~carat,data=diamonds_sub)
    
    unname(predict(fit, data.frame(carat = input$lm)))
  })
```

Based on the selected subset and the carat value a predicted price value is printed in the UI.



```
[1] 21012.92
```

Links and Appendix
========================================================

- Shiny app: https://halici.shinyapps.io/Gapminder-Data-Visualization-using-Shiny-and-Plotly/
- Source Code: 
- Presentation is available via RPubs: 
