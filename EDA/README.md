We ultilized matplotlib and seaborn to create boxplots, scatterplots, and distplots to depict the relationship between certain features and the code column (which we were trying to predict).

Below is a brief list of some of things that we learned about our features through EDA: 

1. Start speed has to be >= 60 mph generally to be a strike
2. End Speed has to be >= 60 mph generally to be a strike
3. Nasty is completely irrelevant, any values of nasty has equal potential as any other value to be a strike
4. Zone can be any value besides 10 for a strike to occur
5. Spin Rate is always >= 3500 for a strike to occur
6. All values for Spin Dir result in strike, does not appear to be super useful
7. -2 < px < 2 allows for a strike
8. -1 < pz < 5 allows for a strike
9. Moreorless all values of pfx_x gurantee a strike
10. Moreorless all values of pfx_z gurantee a strike
11. Almost all values of b_score gurantee a strike, on occassion a value from 13-15 will not result in a strike
12. -60 < break_angle < 60 gurantee a strike
13. 0 < break_length < approx. 20 gurantee a strike
14. 23.5 and above for break_y generally are strikes, 23.5 < break_y < 24.0 gurantees a strike
