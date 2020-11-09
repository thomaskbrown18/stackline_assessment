# Stackline Assessment - Thomas Brown:

To run this program, please download the data (data.csv) and the notebook, and run the cells. Please make sure you have the proper packages installed.

Packages required:
- Numpy
- Pandas
- SciKitLearn
- StasModels
- Scipy
- Seaborn
- Matplotlib

# Q1:
For this question, I needed to do the following:
- Plot the data
- Fit the data
- Determine optimal selling price

To plot the data, I used a scatterplot due to their ease of understanding and ability to add in the color feature for revenue. As you can see below, the y axis is sales, the x axis is price, and the hue is revenue (sales x price). 

![Imgur](https://i.imgur.com/MnKx8Lu.png)

Next, I started with a baseline model. For the baseline model, I'll be using a simple linear model. As you can see in the visualization, a polynomial model will likely be much more accurate (as there's a clear curve to the patter of the data), but I'll be using that for the improved model. It's always important to get a baseline model down so you can be sure the more complex model actually improves accuracy!

I modeled each product separately, and came up with an R2 value of roughly .64 for each model. Given the data, there was much room for improvement here. As you can see in the QQ Plot for product A below, the model is clearly missing something.

![Imgur](https://i.imgur.com/zoaHrqC.png)

Next, I did a polynomial model, using Price squared to help fit the curve. This model worked much better as you can see from the visualization below:

![Imgur](https://i.imgur.com/0lxN06j.png)

While I now have sales modeled, this was only half the equation. I need to find out what price to set. For this, I chose to maximize revenue. Anyone can maximize sales by dropping the price drastically, but this does not help the company, as they would likely lose money. I used the curve I modeled for each product to now show a revenue curve, showing different revenue levels in millions at each different price. The goal for price setting is to maximize this function. Maximizing profit would be ideal, but as I don't know the cost to produce Product A or B, revenue will have to do!

![Imgur](https://i.imgur.com/3YsoRJD.png)

As you can see, revenue is maximized for each product at around a set price of $7. A few lines of code later, I determined a more precise ideal price given the revenue curve I derived from the polynomial model:

![Imgur](https://i.imgur.com/eBUURCC.png)

# Question 2:

For this question, I had to determine the ideal combination of product and website for a set of 3 products and 3 websites, Amazon, Walmart, and Target. There are a few ways to think about this problem, but I chose to think of it in the following way:

To start, I created a numpy array with the data.

![Imgur](https://i.imgur.com/2CliPYX.png)

Next, I separated out the specific websites and products. After that, I divided each cell in each row (store/website) by the proportion of traffic that store recieved (50%, 30%, and 20%). After that, I was left with this matrix, showing that Target with Product C was the winner with a cell-value of 185! We can see that Target outperforming given that of the Product C sold at all the websites, it did not follow the 50%, 30%, 20% pattern one might expect. Rather, it leaned much more heavily to Target. Essentially, this analysis shows that Target with Product C is the best combination in terms of customer conversion as they sold much more Product C than one might expect with their low 20% share of total customers.

![Imgur](https://i.imgur.com/t7lBHqO.png)

Thanks for reading and please let me know your thoughts!

-Thomas
