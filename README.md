##Animated Data Visualization: Gapminder Insights with R 🌏📊

#Overview

This project explores global development trends using the Gapminder dataset. The animated visualization showcases GDP per capita vs. life expectancy over time, categorized by continent.

🚀 Key Features##
Animated visualization of GDP per capita and life expectancy trends.
Faceted view for Africa, America, Asia, and Europe.
Filtered data (GDP < 7000) for clearer insights.
Upward trends in life expectancy as GDP increases.
Notable disparities between continents, with Africa showing high variability.

📈 Visualization Insights
Countries with higher GDP per capita tend to have higher life expectancy.
Africa shows significant variability, highlighting economic and healthcare challenges.
The animation clearly illustrates progress over decades, especially in Asia and America.

💡 Tools & Libraries Used
R Programming Language
ggplot2 - for data visualization
dplyr - for data manipulation and cleaning
gganimate - for creating animations

🛠️ Installation & Setup
Install required R packages:
install.packages(c("ggplot2", "dplyr", "gganimate", "gapminder", "gifski"))
library(ggplot2)
library(dplyr)
library(gganimate)
library(gifski)
library(gapminder)

📜 Code Snippet
gapminder%>%
  filter(continent %in% c("Africa", "Americas", "Asia", "Europe"))%>%
  filter(gdpPercap<7000)%>%
  ggplot(mapping = aes(x = gdpPercap, y = lifeExp))+
  geom_point(aes(colour = continent))+
  theme_bw()+
  facet_wrap(~continent)+
  labs(title = "Year: {frame_time}")+
  transition_time(year)+
  ease_aes("linear")
