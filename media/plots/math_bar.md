bigclass %>% group_by(sex) %>% summarise(avg = mean(Math)) %>% plot_ly(x=~sex, y=~avg, type='bar')
