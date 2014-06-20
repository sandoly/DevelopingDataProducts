---
title       : Introducing myCalories App
subtitle    : Developing Data Products, Coursera
author      : Szabolcs Sandoly
job         : R & Shiny Rookie
framework   : io2012	    # {io2012, html5slides, shower, dzslides, ...}
highlighter : prettify		# {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootsrtap, mathjax, shiny, interactive]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
ext_widgets : {rCharts: [libraries/highcharts]}

---

## Yet another app? for what?

- Healthy lifestyle begs for being aware of daily calories intake
- Methods for determining energy needs: 
	- indirect calorimetry (equipment based) 
	- predictive equations (Harris-Benedict, Mifflin-St.Jeor)
	- quick and dirty method (calories per body weight)
- Harris-Benedict usally overestimates needs (27% of times), while Mifflin-St.Jeor predicts better
- calories per body weight method developed for time sensitive clinical settings 
- myCalories application:
	- asks users to input age, gender, weight in kg, and height in cm   
	- compares Miflin-St.Jeor vs. calories per body weight equations
	- displays macronutrients breakdown in calories and grams
  

--- 

## Mifflin-St.Jeor Equation

- Mifflin-St.Jeor equation outputs Resting or Basal Metabolic Rate (RMR) 
	- measurement of how many calories the body burns at rest
	- men: RMR = $9.99 * weight[kg] + 6.25 * height[cm] - 4.92 * Age + 5$  
	- women: RMR = $9.99 * weight[kg] + 6.25 * height[cm] - 4.92 * Age - 161$
	- predicts within 10% of measured RMR than any other equation
- To take activity level account RMR needs to be multiplied by an activity factor of 1.2-2, where:
	- sedentary (little or no exercise) : RMR x 1.2
	- lightly active (light exercise/sports 1-3 days/week) : RMR x 1.375 
	- moderately active (moderate exercise/sports 3-5 days/week) : RMR x 1.55 
	- very active (hard exercise/sports 6-7 days a week) : RMR x 1.725
	- extra active (very hard exercise/sports and physical job or 2x training) : RMR x 1.9 

---

## Calories per Body Weight & Macronutrients

- Easy and fast way to calculate calorie ranges for individuals in clinical settings


|  Desired Outcome   |             Multiply              |
|:------------------:|:---------------------------------:|
|   To lose weight   | 20-25 calories per kg body weight |
| To maintain weight | 25-30 calories per kg body weight |
|   To gain weight   | 30-35 calories per kg body weight |

Table: Energy needs: Cal / kg
    
- Macronutrient distribution ranges (Dietary Guidelines for Americans,2010)


|  Macronutrient  |  Children, 1-3 years  |  Children, 4-18 years  |  Adults > 18 years  |
|:---------------:|:---------------------:|:----------------------:|:-------------------:|
|  Carbohydrate   |        45-65%         |         45-65%         |       45-65%        |
|       Fat       |        30-40%         |         25-33%         |       20-35%        |
|     Protein     |         5-20%         |         10-30%         |       10-35%        |

Table: Macronutrient Distribution Range: Percent of Energy/Calories

---

## myCalories demo highlight (shiny + highcharts)

![](../assets/img/myCalories.PNG)



