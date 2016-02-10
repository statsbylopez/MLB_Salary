# MLB_Salary

Code for my first [gganimate](https://github.com/dgrtwo/gganimate)!

```{r}
p <- ggplot(mlb.anime, 
  aes(log.Salary, WinP, frame = Year)) +
  scale_x_continuous("log(Salary)") +
  scale_y_continuous("Winning percentage", breaks = 3:7/10, 
                     labels = c("30%", "40%", "50%", "60%", "70%"))  +
  ggtitle("MLB win % by salary,") +
  geom_text(aes(label=Tm))+ Five38Thm
  ```
