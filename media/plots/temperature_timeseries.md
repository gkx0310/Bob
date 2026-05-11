# R code to generate Machine Temperature Over Time plot
library(plotly)

# Assuming X009 dataframe is loaded and available
# Convert Timestamp to datetime objects
X009$Timestamp <- as.POSIXct(X009$Timestamp, format = "%d/%m/%Y %H:%M")

# Create the Plotly plot
p <- plot_ly(X009, x = ~Timestamp, y = ~Temperature, type = 'scatter', mode = 'lines+markers', 
             marker = list(size = 8, color = '#0072B2'), line = list(color = '#0072B2', width = 2))
p <- p %>% layout(title = list(text = 'Machine Temperature Over Time', font = list(size = 20)),
                  xaxis = list(title = list(text = 'Timestamp', font = list(size = 18)), tickfont = list(size = 14)),
                  yaxis = list(title = list(text = 'Temperature', font = list(size = 18)), tickfont = list(size = 14)),
                  plot_bgcolor='white', paper_bgcolor='white')

# To view the plot (optional, as it's saved as HTML)
# print(p)
