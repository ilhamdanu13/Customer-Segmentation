# Customer-Segmentation
# Import Package
import common package
import **numpy as np**

import **pandas as pd**

import **matplotlib.pyplot as plt**

from **kmodes.kprototypes** import **KPrototypes**

from **tqdm.auto import tqdm**

# Import Data
The data set refers to clients of a wholesale distributor. It includes the annual spending in monetary units (m.u.) on diverse product categories (source: https://archive.ics.uci.edu/ml/datasets/wholesale+customers).

Attribute informastion:
1) FRESH: annual spending (m.u.) on fresh products (Continuous);
2) MILK: annual spending (m.u.) on milk products (Continuous);
3) GROCERY: annual spending (m.u.)on grocery products (Continuous);
4) FROZEN: annual spending (m.u.)on frozen products (Continuous)
5) DETERGENTS_PAPER: annual spending (m.u.) on detergents and paper products (Continuous)
6) DELICATESSEN: annual spending (m.u.)on and delicatessen products (Continuous);
7) CHANNEL: customersâ€™ Channel - Horeca (Hotel/Restaurant/CafÃ©) or Retail channel (Nominal)
8) REGION: customersâ€™ Region â€“ Lisnon, Oporto or Other (Nominal)

# Determine the Number of Cluster
How to determine the number of clusters can simply use intuition, or if based on data using elbow analysis. Our data contains categorical and numerical columns, so we will use K-Prototypes. K-Prototypes is a combination of K-Means with K-Modes (numeric and categorical).

![image](https://user-images.githubusercontent.com/86812576/171774929-1cfc6724-28a5-4d7f-9ab8-fe4a659c162c.png)

We can see from the elbow analysis results, then we can use 3 or 5 clusters. But I will choose 3 clusters.

# Training

![Screenshot 2022-06-03 093546](https://user-images.githubusercontent.com/86812576/171775640-99dabfc5-cc1e-440f-93b4-ed1c54f6fc98.png)

In training, I added a column named "Cluster".
The goal is to know that each customer belongs to which cluster.

# Analyze Cluster

The numbers in the table below are not just averages but are cluster centers. the example is in this case with 3 clusters, then each of these numbers represents each centroid.

![Screenshot 2022-06-03 094754](https://user-images.githubusercontent.com/86812576/171776878-3fa7e01d-b480-4f73-8720-bcd074eb2bc6.png)

Customer Segmentation:
- Cluster 0 = frugal people
- Cluster 1 = type of people who shop for fresh food.
- Cluster 2 = type of people who shop for milk, grocey and detergents paper

I have grouped all customers into 3 types of people. Cluster 0 can be seen that people in the first type buy goods at relatively cheap prices. so I define the first type of people as frugal.

In cluster 1, it can be seen in the table that they are customers who really like to buy "Fresh" food, as well as consumption of "Frozen", and "Delicassen" is almost double the average. I simply refer to cluster one as the type of people who shop for fresh food.

In the cluster 2, it can be seen that for the purchase of "Milk", "Grocery", and "Detergents_Paper" the annual expenditure is greater than the other two clusters. while the purchases of "Fresh", "Frozen" and "Delicassen" are below the average from other clusters. For this reason, I simply refer to cluster two as the type of people who shop for milk, grocey and detergents paper.

