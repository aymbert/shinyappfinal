# shinyappfinal

Description

Title: Selectize rendering methods
Author: RStudio, Inc.
AuthorUrl: http://www.rstudio.com/
License: MIT
DisplayMode: Showcase
Tags: selectize
Type: Shiny


In this example, we use the method session$registerDataObj() to register a data object in the shiny session, which we can retrieve via the URL that this method returns (mapurl here). Then we update the selectize input so that the choices can be processed on the server side (server = TRUE), and we provide a custom rendering method via the selectize initialization options. The rendering method sends a query to mapurl with the query variable state, which takes the values of the options (item.value).

We also provided the filter function in session$registerDataObj(), which should return an HTTP response based on the data registered and the current request req. We can extract the query string from req$QUERY_STRING, and parse the state string. Once we have got the state name, we draw a map of the state as well as a pie chart of the urban population percentage. Finally the plot is returned as an HTTP reponse that has the MIME type image/png, and <img> tag in the selectize rendering method will get the requested image.

This app also contains a parallel coordinate plot (renderPlot) and a data table (renderDataTable) that are straightforward to understand and should be familiar to Shiny users.
