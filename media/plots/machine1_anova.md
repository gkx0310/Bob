library(tidyverse)
library(plotly)
library(htmlwidgets)
df_m1 <- X009 %>% filter(Machine == 1)
df_m1$Pressure_f <- factor(df_m1$Pressure)
df_m1$Temperature_f <- factor(df_m1$Temperature)
okabe_ito_colors <- c("#E69F00", "#56B4E9", "#009E73", "#F0E442", "#0072B2", "#D55E00", "#CC79A7", "#999999")
p <- plot_ly(data = df_m1, x = ~Pressure_f, y = ~PartResistance, color = ~Temperature_f, type = "box", colors = okabe_ito_colors) %>%
    layout(
        title = "PartResistance by Pressure and Temperature (Machine 1)",
        xaxis = list(title = "Pressure (kPa)"),
        yaxis = list(title = "PartResistance (Ohms)"),
        shapes = list(
            list(
                type = "line",
                xref = "paper", yref = "y",
                x0 = 0, x1 = 1,
                y0 = 10, y1 = 10,
                line = list(color = "red", dash = "dash")
            )
        ),
        annotations = list(
            list(
                x = 1, y = 10,
                xref = "paper", yref = "y",
                text = "USL = 10 (Lower is Better)",
                showarrow = FALSE,
                xanchor = "right", yanchor = "bottom",
                font = list(color = "red")
            )
        )
    )
htmlwidgets::saveWidget(p, "media/plots/machine1_anova.html", selfcontained=TRUE)

