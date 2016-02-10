# MLB_Salary

Code for my first [gganimate](https://github.com/dgrtwo/gganimate)!

```{r}
library(gganimate)
require(RCurl)
library(ggplot2)
mlb.anime <- read.csv(text = getURL(
  "https://raw.githubusercontent.com/statsbylopez/MLB_Salary/master/mlb.anime.csv"))
  
p <- ggplot(mlb.anime, 
  aes(log.Salary, WinP, frame = Year)) +
  scale_x_continuous("log(Salary)") +
  scale_y_continuous("Winning percentage", breaks = 3:7/10, 
                     labels = c("30%", "40%", "50%", "60%", "70%"))  +
  ggtitle("MLB win % by salary,") +
  geom_text(aes(label=Tm))+ 
  theme_bw()

gg_animate(p)
  ```
