#
# This is a Shiny web application. You can run the application by clicking
# the 'Run App' button above.
#
# Find out more about building applications with Shiny here:
#
#    http://shiny.rstudio.com/
#

library(shiny)


D_DB = 2.25
E_GG = 2.5
G_U = 1.75
M_U = 1.75



# Define UI for application that draws a histogram
ui <- fluidPage(
   
   # Application title
   titlePanel("Mercat Hours"),
   
   # Sidebar with a slider input for number of bins 
   sidebarLayout(
      sidebarPanel(
        p("For normal tours, input the number of tours you are doing"), 
        numericInput("DDB", h3("DDB"), value = 0),
         numericInput("EGG", h3("EGG"), value = 0),
         numericInput("GU", h3("GU"), value = 0),
         numericInput("MU", h3("MU"), value = 0),
        p("For private bookings, input the number of hours (e.g. 1.5 hours), including the extra .5 hours paid for the beginning and end of tours"),
         numericInput("PB", h3("PB"), value = 0)
      ),
      
      # Show the number of hours
      mainPanel(
         h1("Total number of hours"),
         textOutput("total_hours")
      )
   )
)

# Define server logic required to draw a histogram
server <- function(input, output) {
  
  total_hours = reactive({(input$DDB * D_DB) + (input$EGG * E_GG) + (input$GU * G_U) + (input$MU * M_U) + input$PB})
  
  output$total_hours <- renderPrint({ paste("You are working",total_hours(),"hours") })
   
}

# Run the application 
shinyApp(ui = ui, server = server)

