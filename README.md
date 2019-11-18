World Wide Products Inc
==============================

Shipping and delivering to a place near you

Author: Ruturaj Kiran Vaidya

Project Organization
------------

    ├── LICENSE
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting

--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>

### Before Getting Stated

If you are only interested in looking at the notebook then go to (There are notebook rendering problems in github ecosystem):

https://nbviewer.jupyter.org/github/Ruturaj4/world_wide_products_inc/blob/master/notebooks/1.0-rkv-world-wide-products-inc.ipynb

All the graphs are plotted using `matplotlib`.

### Aim
<ul>
<li>Load the dataset and do feature engineering</li>
<li>Select a product based on analysis</li>
<li>Determine demand for that product using time-series forecast models</li>
</ul>

### Dataset used

Dataset: https://www.kaggle.com/felixzhao/productdemandforecasting

This dataset contains product information.

### Discussion

First, I imported the dataset and I selected "Product_1359", as this is the top product (i.e. having the highest count, or data). Then I cleaned up the dataset (feature engineering) and only selected "Date" and "Order_Demand" for the product Product_1359. Other columns don't give useful information for our analysis. I then plotted various visualizations, to get to know the dataset. Following graphs show order demand for the product (daily and monthly), as first graph is kind of chaotic, I sum up the order demand per month and decided to use that, to get the clear picture for further analysis. I also removed the data of Jan 31 of 2017, as there were fewer values.

![alt text](/reports/figures/order_demand_all.png)
![alt text](/reports/figures/order_demand_few.png)

Next, it is importatnt to reason that the data is stationary. This is known as stationarity of the dataset. It is important for the model training (I actally found this in a youtube video). I used rolling mean and standard deviation methods (actually these methods show mean and deviation, and we can determine the stationarity by looking at the graph - there is a video which describes this - https://www.youtube.com/watch?v=e8Yw4alG16Q&t=1245s, but I think I should do more rearch on this in the future) as well as Dickey-Fuller method to determine the stationarity. Following figure shows the graph of rolling mean and standard deviation.

![alt text](/reports/figures/rolling.png)

The following decomposition graph visualizes general trends

![alt text](/reports/figures/decomposition.png)

Lastly, I used ARIMA model for forecasting. I splitted product data into training and testing parts (roughly 80-20%), to verity the forecasting of the model.

![alt text](/reports/figures/forecast.png)

### License

<b>MIT</b>
