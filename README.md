# :trophy::girl: Assignment 2 MapReduce Algorithm :trophy:




## About Dataset
The data consists of flight arrival and departure details for all commercial flights within the USA, from October 1987 to April 2008. 
We have a dataset of size 1.6 GB (compressed, and 12 GB when uncompressed), with the records of nearly 120 million records. Our goal is to use map-reduce algorithm to get the **count** of **number of flights** for each carrier.
Each row represents an individual flight record with details of that flight in the row. The information are:

- Time and date of arrival
- Originating and destination of airports
- Amount of time for a plane from taxi to takeoff

You can find more information about this dataset in the website of [Statistical Computing](http://stat-computing.org/dataexpo/2009/).


## About Map-Reduce Algorithm :
MapReduce implements various mathematical algorithms to divide a task into small parts and assign them to multiple systems.It is a software framework for processing large datasets using several machines.The Objective of MapReduce Algorithm is to map data into (key, value) pairs and reduce all pairs with same key.
MapReduce has 3 steps:

Mapping step – Produce intermediate results & associates with an output key
Shuffling step – Group intermediate results with same output key
Reducing step – Process groups of intermediate results with same output key

## Instructions for running the program using Algorithm:
The goal is to find the carrier counts and  I used two ways of getting counts of carriers:

1.First we will code in a  serial way which  requires to loop through all of the records and update one by one.

2.For MapReduce Algorithm way :This code is divided into 3 steps:

1. Map Phase
    - For each line of flight data, extract the carrier code and make a key value pair. (ex: ('THY', 1))
2. Shuffle and Sort Phase
    - Read the list of pairs from the map phase.
    - Group all the values of each key together (ex: all THYs, Uniteds, etc.)
    - Sort the data by the key
3. Reduce Phase
    - Read each key and list of values from Shuffle and Sort phase.
    - Add the total # of ones in the carrier code's list together


