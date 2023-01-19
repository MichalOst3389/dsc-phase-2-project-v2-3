README

In the project, I aimed to give sound advice for a company by the name of KC real estate.  KC real estate came to me and asked me to analyze data from the King's County Housing dataset so that they could get a better idea of where to invest 10 million dollars.

After cleaning the data to
-remove empty values that would skew data,
-remove NaN values,
-took rows that had a year for renovation and added a column to include True or False
-ran OLS regression
-switch values to numerical values

-Location

After running OLS regression to see the r- squared and P value of the dependent variable (price) and zipcode, the r-squared was only 0.003, so i decided to look more at latitude and longitude instead.  While the r-squared value of lat/long was still relatively low at 0.098,  it still gave me a better indication of how the location effected the price. 



![Screenshot 2023-01-08 224853](https://user-images.githubusercontent.com/87345982/212143008-b5a34272-c205-400f-9820-16228d344928.png)

I realized after this, that a better way to scope out good houses to buy was to use a heatmap instead.
For location I decided to create a heat map with the hue set to price.  This gave me a good idea of where to focus the my search.  I realized that the more valuable information was where NOT to search for a house to buy, as most of the map was covered in red plots (red is cheapest, green is the most expensive houses).  This told me to stay away from the coordinates between latitude 47.5, and 47.7, longitude -122.2 and -122.2.  

![heatmap](https://user-images.githubusercontent.com/87345982/213468672-b3214494-30e4-424a-9537-9ab758e6f9be.png)


-Price

While performing data analysis, I plotted pair plots including price, bedrooms, bathrooms, square foot living space, and grade.  I found that while the number of bedrooms dont have much of an effect on price, bathrooms, square footage, and grade made the price go up.  I also noticed that the profit on houses that were cheaper and renovated, was better than the profit from a more expensive house.  
![Screenshot 2023-01-08 225039](https://user-images.githubusercontent.com/87345982/211238329-d2323124-9fe6-4c5c-9b49-6f479121a89f.png)

![% vs price increase](https://user-images.githubusercontent.com/87345982/212144300-1cf30029-2c07-400d-903f-aa7b90e541f5.png)


-example investment opputunities
While searching for good examples of homes, I found random samples and passed them through my regression model.  as I did that I focused on what would make the price of a house go up, while also keeping in mind that many places have laws about how much you can add on to your house, and went with 50% add on as the limit of square footage to be added.  Renovations are also house specific.  Without seeing the house theres not a good way to get an indication if a basement has to be renovated for example.  3 houses were found quickly that would fit the mold of my recommendations to make money off these properties.
    
-Renovations
Doing some analysis here by running an OLS regression, I was able to see that a good variable to compare to price was square footage.  The r-squared value was 0.493 which told me there was a strong correlation between livable square footage and price. 

![OLS for sqft vs prce](https://user-images.githubusercontent.com/87345982/212144879-0ec2997f-92cf-47c4-aeea-0526bd42cebe.png)

I decided to create a scatter plot to better visualize this.
![sqft vs price](https://user-images.githubusercontent.com/87345982/212145157-f1647503-29c1-4c42-a41e-25ddd3795f08.png) 


When it comes to renovations, according to rocket mortgage and national association of home builders, there are certain percentages of your homes value that should not be exceeded when renovating certain room.  I created a function that will take in an original cost of home, and tell you exactly how much money should be spent on each room to be renovated. 
  ![NAOHB](https://user-images.githubusercontent.com/87345982/211238421-e1608b97-c8eb-40bd-8d43-b008aac762b4.png)
  
-To calculate the profit per dollar invested, you would divide the total profit by the amount invested. In this case, the profit per dollar invested would be 1,204,938 / 10,000,000 = 0.1204.  I found that we could make a profit of 12 cents per dollar if following my recommendations.

To summarize, the King's County Housing dataset was analyzed in order to provide investment recommendations for KC Real Estate. After cleaning the data and running OLS regression, it was determined that the data was ready for analysis due to a p-value of less than 0.05 and an R-squared value of 0.659. The independent variables of location, renovations, and whether or not the house's price was over a million were chosen for further analysis. A heat map was created to identify the most and least expensive locations, and three potential investment opportunities were identified based on factors such as the number of bathrooms, square footage, and grade. A function was also created to recommend appropriate renovation budgets based on the value of a home. By following these recommendations, it was estimated that a profit of 0.1204 dollars per dollar invested could be made.
