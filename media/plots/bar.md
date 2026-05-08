bigclass %>% count(age) %>% plot_ly(x = ~age, y = ~n, type = 'bar')
