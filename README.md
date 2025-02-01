🌍 Animated Data Visualization: Gapminder Insights with R 📊

Overview
This project visualizes global development trends using the Gapminder dataset. It highlights GDP per capita vs. life expectancy over time, segmented by continent.

🚀 Key Features:
Animated visualization of GDP per capita vs. life expectancy.
Faceted views for Africa, America, Asia, and Europe.
Filters data to show countries with GDP less than $7000 for clearer insights.
Illustrates upward trends in life expectancy with increasing GDP.
Highlights disparities, with Africa showing high variability.

📈 Visualization Insights:
Higher GDP per capita correlates with higher life expectancy.
Africa shows significant variability, emphasizing economic and healthcare challenges.
The animation effectively demonstrates progress, particularly in Asia and the Americas.

💡 Tools & Libraries Used:
R Programming Language
ggplot2: Data visualization
dplyr: Data manipulation
gganimate: Animation creation

🛠️ Installation & Setup:
Install required R packages:
install.packages(c("ggplot2", "dplyr", "gganimate", "gapminder", "gifski"))
library(ggplot2)
library(dplyr)
library(gganimate)
library(gifski)
library(gapminder)

📜 Code Snippet:
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


