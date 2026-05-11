library(plotly)
X009$Timestamp <- as.POSIXct(X009$Timestamp, format = "%d/%m/%Y %H:%M")
p <- plot_ly(X009, x = ~Timestamp) %>%
  add_lines(y = ~Temperature, name = "Temperature", line = list(color = "#0072B2")) %>%
  add_lines(y = ~Pressure, name = "Pressure", line = list(color = "#D55E00"))
