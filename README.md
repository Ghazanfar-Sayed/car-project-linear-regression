# Predicting Used Car Prices with Linear Regression

In this project, I worked through a typical data science setup to try and predict how much a used car might sell for. The goal was to build a linear regression model that could take in a few basic details about a car—like its brand, how many miles it's driven, and its age—and give a reasonable estimate of its price.

## The Data

I used a dataset called real_life_example.csv, which contains details for over 4,000 cars. It includes columns for Brand, Price, Body, Mileage, Engine Volume, Engine Type, Registration, Year, and Model.

## How I approached the project

When I first looked at the data, it was clear that it needed quite a bit of cleaning before any modeling could happen.

First, I had to deal with the missing values. I found that about 170 entries were missing prices and 150 were missing engine volumes. Since these are pretty critical for a price prediction model, I decided to drop those rows entirely.

I also noticed that the 'Model' column had over 300 unique entries. This would have made the model way too complex once I turned them into categorical variables, so I decided to drop that column to keep things simpler and more focused on the bigger drivers of price.

Another big step was handling outliers. For example, some cars had mileage or price values that were way beyond the norm. I kept only the data within the 99th percentile for these columns to prevent a few extreme cases from skewing the whole model. I also removed cars with an engine volume listed over 6.5, as those usually aren't realistic for standard passenger vehicles.

## Building the Model

Linear regression works best when the data follows certain assumptions. I checked the distribution of the price and realized it wasn't linear when compared to mileage or age. To fix this, I took the natural log of the price. This smoothed things out and helped the model perform much better.

For things like brand and engine type, I created dummy variables so the computer could understand them as categories. I was careful to drop one category from each set to avoid the technical issue known as the "dummy variable trap."

After splitting the data into training and testing sets (80/20), I scaled the features so they were all on a similar level.

## Results

After all that prep work, the model ended up with an R-squared score of around 0.77. This basically means the features I chose—like brand, age, and mileage—explains roughly 77% of why car prices vary the way they do in this dataset.

I also checked the residuals (the difference between what the model predicted and the actual price). They looked well-distributed around zero, which tells me the model's logic is pretty solid for this kind of data.

## Running the code

If you want to run this yourself, you'll need the standard Python data stack. You can install everything with:

pip install numpy pandas matplotlib seaborn scikit-learn

Just open the script.ipynb file in a Jupyter environment and make sure the CSV file is in the same folder.
