
plot_df <- X009 %>% filter(Machine == 1, Temperature == 303, Pressure == 100)
q <- qcc(plot_df$PartLength, type = 'xbar.one')

