# Bar-Chart-on-R
Using R programming I created a chart and histogram with an inbuilt data on R called msleep


library(tidyverse)
data()
view(msleep)

name(msleep)
list(msleep)

msleep %>%
  drop_na(vore) %>%
  ggplot(aes(x = vore))+
  geom_bar(fill = "#97B3C6")+
  #coord_flip()+
  theme_bw()+
  labs(x = "vore",
       y = NULL,
       title = "Number of Observation")

#Flip your chart 
msleep %>%
  drop_na(vore) %>%
  ggplot(aes(x = vore))+
  geom_bar(fill = "red")+
  coord_flip()+
  theme_bw()+
  labs(x = "vore",
       y = NULL,
       title = "Number of Observation")

#create your chart in order
msleep %>%
  drop_na(vore) %>%
  ggplot(aes(fct_infreq(vore)))+
  geom_bar(fill = "green")+
  #coord_flip()+
  theme_bw()+
  labs(x = "vore",
       y = NULL,
       title = "Number of Observation")


msleep %>%
  drop_na(vore) %>%
  ggplot(aes(fct_infreq(vore)))+
  geom_bar(fill = "green")+
  #coord_flip()+
  theme_bw()+
  labs(x = "vore",
       y = "Total sleep",
       title = "Number of Observation")


#change the label of X axis
msleep %>%
  drop_na(vore) %>%
  ggplot(aes(x = vore))+
  geom_bar(fill = "#97B3C6")+
  #coord_flip()+
  theme_bw()+
  labs(x = "who eats what?",
       y = NULL,
       title = "Number of Observation")

msleep %>%
  ggplot(aes(x = awake))+
  geom_histogram(binwidth = 2, fill = "#97B3C6")+
  theme_bw()+
  labs(x = "Total sleep",
       y = NULL,
       title = "Histogram on total sleep")

msleep %>%
  ggplot(aes(x = awake))+
  geom_histogram(binwidth = 2)+
  theme_bw()+
  labs(x = "Total sleep",
       y = NULL,
       title = "Histogram on total sleep")

msleep %>%
  ggplot(aes(x = awake))+
  geom_histogram(binwidth = 2, fill = "#97B3C6")+
  coord_flip()+
  theme_bw()+
  labs(x = "Total sleep",
       y = NULL,
       title = "Histogram on total sleep")

msleep %>%
  ggplot(aes(awake))+
  geom_histogram(binwidth = 2, fill = "#97B3C6")+
  theme_bw()+
  labs(x = "Total sleep",
       y = NULL,
       title = "Histogram on total sleep")

mean("Total sleep")
