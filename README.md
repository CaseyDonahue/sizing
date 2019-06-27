# Social Sizing
### Purpose
This application was created to be used in the ecommerce retail industry to decrease the probability of ordering clothes in the wrong size by determining the mean z-score and percentile of a user (U1). This value could then be compared to the z-score of a pervious user (U2) who had sent in a picture and review of the clothing in question. With this, U1 can see how the item fit someone else with a similar body type before placing their final order.
Additionally, the code gives estimates of any measurements not provided by the user by working backwards from their average z-score. The feature provides additional data for the host platform to store and utilize as well as consumer user for comprison to a brands size chart.
### Background and Data Sources
It is a widely accepted notion that the majority of human measurements fall on a bell curve scale. The majority of people are of medium size, with decreasing proportions of the population going towards either extreme. This model ignores the fact that this must be a forced right-skew as no body measurement can be below zero but can theoretically expand infinetely. 
The two models use the same algoritm but are based off of two different data sets. The first is using the CDC's *Anthropometric Reference Data for Children and Adults: United States, 2011-2014* which used between 5,000 and 5,500 females. Researchers measured over age 20 for values in weight, height, waist circumfrence, sagittal abdominal length, midarm circumfrence, upper arm length, and upper leg length. Since this report only provided percentiles and not a standard deveation the algoritm used the known z-score for the tenth percentile to find the standard deveation for each measurement. 
The second model uses Size USA's data which was collected from 6,310 female participants in thirteen cities across the United States. They measured height, weight, waist circumference, bust circumference, hip circumference, high-hip circumference, and the back-waist length. The reasoning behind creating a second model with different data stems from the specific measurements used in each. The CDC's data was easier to find but does not use widely known measurements. Size USA uses values that are much more common measurements to clothes shopping.
For the moment, combining the two models would not be the best course of action becuase they used different age groupings to get the mean and standard deviation values used in this process.
### Inputs and Outputs
The only required inputs for the algorithm are a users age and at least one of the requested measurements. However, a greater number of unique measurements provided will make the assigned z-value and subsequent estimations of missing elements more accurate. 
The code will output the population percentile with respect to each measurement entered by the user along with a calculated mean. Additionally, it will give an estimation of any measurements not entered by the participant based on the calculated mean percentile/z-score. Other than text, the code produces a standardized bell curve that illustrates the how far the user's measurements are from the population mean. The color correlation is as follows:

##### CDC Data
1. Weight - Red
2. Height - Cyan
3. Waist Cirucumference - Green
4. Sagittal Abdominal - Dark Violet
5. Midarm Circumference - Orange
6. Upper Arm Length - Yellow
7. Upper Leg Length - Magenta
##### Size USA Data
1. Weight - Red
2. Height - Cyan
3. Waist Cirucumference - Green
4. Bust - Dark Violet
5. Hip - Orange
6. Back-Waist Length - Yellow
7. High Hip - Magenta

The colors above will only appear if a specific measurement was entered by a user. Otherwise, there will be a black marker to represent any/all measurements not entered by using the average z-score of the entered measurements. The dotted line represents the same thing but, unlike the black dot, will always be present, even if all measurements are entered by the participant. 
This average z-score will be used in the way described in the 'Purpose' section.
