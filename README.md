# UK Food Establishment Hygiene Scores

A database of UK Food Establishments was imported from MongoDB using mongoimport and Pymongo. The code used to import the data to the server: 1) cd into resources folder 2) mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json

The database was edited to include an additional new restaurant, adjust the business type ID, and then to remove all Dover establishments. 

## Data Analysis

The estabishments are ranked on four different criteria: Confidence in Management, Hygiene, Structural, and an overall Rating Value. For each of the three category scores, the score is out of 20, and a lower score is considered ideal. For the overall Rating Value, however, the score is 1-5 with a 5 being ideal.

### Hygiene Scores

There are a total of 41 establishments with the worst possible hygiene rating. Below is a snippet from this list:

![image](https://user-images.githubusercontent.com/116215793/226116177-ae373104-3e68-4d97-b2ae-2277fda2f27b.png)

### London Establishments

In London, there are a total of 34 establishments scoring either 4 or 5 on their Rating Values. 10 of these establishments are below:

![image](https://user-images.githubusercontent.com/116215793/226116366-97857331-35a1-4a09-bfe5-1948bff4de41.png)

### Local Best Restaurants

During the inital transformation of the database, an additional entry was added for Penang Flavours, a new restaurant. This was used as the center of a .01 degree radius to determine the top 5 local establishments with ideal Rating Values and the lowest hygiene scores. These five establishments span the gamit of business types, with none being of the restaruant type. This lends to the possibility of Penang Flavours being the highest rated restaurant in the area.

![image](https://user-images.githubusercontent.com/116215793/226116572-6a54c453-8703-435b-9264-f773eb6b60d6.png)

### Most Hygienic Establishments

The full database was queried to determine how many establishments in each area had a perfect hygiene score. Thanet has substantially more hygienic establishments than the other localities. 

![image](https://user-images.githubusercontent.com/116215793/226116721-3bc1aed1-26ba-4aaf-80e3-d6171bd55c9b.png)
