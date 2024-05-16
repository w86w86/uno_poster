In the Data Visualization course at the University of Nebraska Omaha, students learn how to effectively communicate data-driven insights using visual tools and techniques. The course covers topics including principles of design, choosing the right type of visualization for the data, color theory, storytelling with data, and the use of data visualization software like R language.

For the semester project in this course, group of four students was tasked with creating a poster on a subject of their choice. 
We decided to focus on the topic of income growth, income inequality, and poverty in the United States, using graphical representation to explore these issues across different geographies and demographics.

The group has utilized this GitHub repository to organize all the data sources and store the code written in the R programming language. 
The repository includes a notebook file that allows anyone interested to run all the graphical plots at once, thereby facilitating easy reproduction of the study's findings.

The abstract of their project highlights the general increase in real incomes for nearly all demographics in the U.S., suggesting that economic growth has ostensibly improved the standard of living for most Americans. However, it also points out that the benefits of this growth have not been evenly distributed, with some groups and regions reaping more advantages than others.

Graph #1 
> visualizes median income growth by race, indicating that Asians are the top earners
> by a significant margin. It also shows an overall ascending trend in median income
> growth for various races from 2002 to 2022, despite a recent downturn due to the COVID-19 pandemic.
<details>
<summary>Tips for collapsed sections</summary>
   
### Farida
```R
   Data = read.csv("Race of Householder-Households by Median Income.csv")
   #install.packages("ggplot2")
   #install.packages("tidyverse")
   
   library(tidyverse)
   
   library(ggplot2)
   
   data_long <- tidyr::pivot_longer(Data, cols = c(White, Black, Asian, Hispanic),
                                    names_to = "Race", values_to = "Value")
   
   ggplot(data_long, aes(x = Year, y = Value, color = Race)) +
     geom_line(size = 4.5) +
     
     labs(x = "Year", y = "Income", title = "Real Median Income by Racial Group, Asians = Top Earners") +
     scale_y_continuous(labels = scales::comma) +
     theme_minimal() 
```
</details>

Graph #2 
> presents changes in real median household income from 2000 to 2022,
> emphasizing the importance of inflation-adjusted income growth
> for the standard of living and its political implications.

Graph #3 
> depicts the growing income disparity, particularly highlighting
> the stagnation of income for the lowest fifth of the population
> and the doubling of income for the wealthiest Americans every 25 years.
> The graph projects this trend to continue, resulting in an even larger income gap in the future.

Graph #4 examines 
> regional income disparities and shows that the Northeast has the highest median household income,
> hich is increasing at a faster rate than in other regions.
> It notes that this data represents overall household income irrespective of educational attainment.

Through this course and project, we gained hands-on experience in data analysis and visualization, learning how to interpret datasets. This project combines technical skills with critical thinking about social issues, reflecting the real-world applicability of data visualization.
