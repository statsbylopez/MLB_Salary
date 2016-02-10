# MLB_Salary


Last summer, I helped write a [FiveThirtyEight](http://fivethirtyeight.com/features/dont-be-fooled-by-baseballs-small-budget-success-stories/) piece which suggested that the link between team salary and winning percentage remains strong, despite the recent successes of small budget teams. While one of those plots tracked the association between win percentage and salary over the last three decades, I figured it'd be worth using `gganimate` to track by year. Read more about the package [here](https://github.com/dgrtwo/gganimate).

Here's the code! And check out the resulting gif [here](https://twitter.com/StatsbyLopez/status/697266930797932545/photo/1)

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


gganimate is super easy to use, but make sure you have `ImageMagick` downloaded to your computer ([link](imagemagick.org)). That took me a few tries. 
