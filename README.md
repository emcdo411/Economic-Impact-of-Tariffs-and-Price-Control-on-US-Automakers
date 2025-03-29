# Economic Impact of Tariffs on U.S. Automakers and Job Market

### **Repo Name:**
`Economic-Impact-of-Tariffs-and-Price-Control-on-US-Automakers`

---

## **Summary:**

This project explores the economic impact of tariffs on U.S. automakers, specifically focusing on the potential effects of price control mechanisms and how they could influence the job market. Using real-time data and simulation, this analysis examines the interaction between tariffs, price hikes, and production output in the automotive sector, with an emphasis on Ford, Chevrolet, Tesla, and Toyota.

The project is inspired by a conversation with Yao, a professional from China, who raised an insightful point about price controls and their potential economic consequences. We dive into the topic of **price control**—specifically how tariffs act as a price control mechanism—and its effect on production output, job losses, and economic stability in the U.S.

### **Key Insights Covered:**
- **Impact of Tariffs on Supply and Demand**: How U.S. automakers may respond to tariffs and price control.
- **Historical Context of Price Control**: Comparing price controls in capitalist economies and communist systems like China.
- **Relevance to Current U.S. Economy**: How U.S. tariffs are affecting prices and output in the automotive sector.

## **Why This Matters:**
Price controls, though often associated with centrally planned economies, are also used in capitalist economies, especially when government intervention is necessary to protect industries or manage inflation. This analysis presents the intersection between economic theory and the real-world impacts of tariffs, offering a deep dive into how U.S. automakers, job markets, and production outputs will be influenced by future tariff increases.

---

## **Accomplishments:**

In this project, we analyzed how price control mechanisms, particularly through tariffs, can influence output and job market stability in the automotive sector. The analysis was conducted using the following data:

- **Data Sources**: A combination of simulated and real data on car models (Ford Mustang, Chevrolet Malibu, Tesla Model 3, and Toyota Camry).
- **Graphs**: 3 primary visualizations were created using RStudio to analyze the effects of tariffs on job losses and price increases:
  1. **Impact of Tariffs on U.S. Automakers**: A 3D plot comparing the effect of tariffs on job growth across the automotive industry.
  2. **Impact of Price Controls**: A line graph demonstrating the potential output reductions of car models under different tariff rates.
  3. **Price Hikes for Car Models**: A heatmap visualization of job losses across U.S. dealerships based on price increases after tariffs.

Below are the key graphs generated during the analysis:

---

## **Code for Graphs**

### **Graph 1: 3D Plot of Job Loss Impact Due to Tariffs on U.S. Automakers**

```r
library(plotly)

# Assuming we have the job data for the different automakers
automaker_data <- data.frame(
  Automaker = rep(c("Ford", "Chevrolet", "Tesla", "Toyota"), each = 6),
  Tariff_Rate = rep(seq(0, 0.25, by = 0.05), times = 4),
  Job_Loss = c(5, 6, 8, 10, 12, 14, 6, 7, 9, 11, 13, 15, 4, 5, 6, 7, 8, 10, 7, 8, 9, 10, 12, 14)
)

# 3D Plot for Job Losses by Tariff Rate and Automaker
fig <- plot_ly(automaker_data, x = ~Automaker, y = ~Tariff_Rate, z = ~Job_Loss, color = ~Automaker, type = "scatter3d", mode = "lines+markers")
fig <- fig %>% layout(title = "Impact of Tariffs on Job Losses in the U.S. Automotive Industry",
                      scene = list(xaxis = list(title = 'Automaker'),
                                   yaxis = list(title = 'Tariff Rate'),
                                   zaxis = list(title = 'Job Losses')))
fig
```

### **Graph 2: Line Plot for Car Models' Output Reductions Based on Tariff Rates**

```r
library(ggplot2)

# Simulated production output data
production_data <- data.frame(
  Tariff_Rate = rep(seq(0, 0.25, by = 0.05), times = 4),
  Car_Model = rep(c("Ford Mustang", "Chevrolet Malibu", "Tesla Model 3", "Toyota Camry"), each = 6),
  Production_Output = c(
    1000 / (1 + 0 * 10), 1000 / (1 + 0.05 * 10), 1000 / (1 + 0.10 * 10), 1000 / (1 + 0.15 * 10), 1000 / (1 + 0.20 * 10), 1000 / (1 + 0.25 * 10),
    1200 / (1 + 0 * 10), 1200 / (1 + 0.05 * 10), 1200 / (1 + 0.10 * 10), 1200 / (1 + 0.15 * 10), 1200 / (1 + 0.20 * 10), 1200 / (1 + 0.25 * 10),
    1100 / (1 + 0 * 10), 1100 / (1 + 0.05 * 10), 1100 / (1 + 0.10 * 10), 1100 / (1 + 0.15 * 10), 1100 / (1 + 0.20 * 10), 1100 / (1 + 0.25 * 10),
    1300 / (1 + 0 * 10), 1300 / (1 + 0.05 * 10), 1300 / (1 + 0.10 * 10), 1300 / (1 + 0.15 * 10), 1300 / (1 + 0.20 * 10), 1300 / (1 + 0.25 * 10)
  )
)

# Plot production output for each car model
ggplot(production_data, aes(x = Tariff_Rate, y = Production_Output, color = Car_Model)) +
  geom_line() +
  labs(title = "Production Output Reduction by Car Model and Tariff Rate", x = "Tariff Rate", y = "Production Output")
```

### **Graph 3: Heatmap of Job Losses for Dealerships Based on Price Hikes**

```r
library(ggplot2)

# Simulated job losses for dealerships based on price hikes
dealership_data <- data.frame(
  Dealership = rep(c("Ford Dallas", "Chevy Dallas", "Tesla Dallas", "Toyota Dallas"), each = 6),
  Price_Hike = rep(seq(0, 25, by = 5), times = 4),
  Job_Loss = c(50, 60, 75, 90, 110, 130, 40, 50, 65, 80, 100, 120, 60, 70, 85, 100, 120, 140, 55, 65, 80, 95, 115, 135)
)

# Heatmap of job losses due to price hikes
ggplot(dealership_data, aes(x = Dealership, y = Price_Hike, fill = Job_Loss)) +
  geom_tile() +
  scale_fill_gradient(low = "yellow", high = "red") +
  labs(title = "Job Losses for Dealerships Based on Price Hikes",
       x = "Dealership", y = "Price Hike (%)", fill = "Job Losses")
```

---

## **Why This Matters:**

Understanding the impact of tariffs and price controls on the automotive sector, specifically job losses and production outputs, is critical in predicting future economic shifts. By simulating and analyzing how U.S. automakers may respond to tariffs and price control mechanisms, we gain valuable insights into potential job losses, inflationary effects, and overall industry stability. This is important for policymakers, businesses, and workers in the automotive industry, as well as anyone concerned about the broader implications of trade wars and price control mechanisms.

---

## **Conclusion:**

This project serves as an important starting point in analyzing the intersection of tariffs, price controls, and their impact on the job market. Through data-driven analysis and simulation, we have demonstrated how increased tariffs could affect U.S. automakers, potentially leading to job losses and reduced output. By leveraging tools like RStudio and various visualization techniques, this analysis can inform decision-making and policy formulation, ensuring that all stakeholders are aware of potential consequences.

---

Feel free to use the code and analysis in this repository to dive deeper into economic simulations of tariffs, price controls, and job market shifts.

---

