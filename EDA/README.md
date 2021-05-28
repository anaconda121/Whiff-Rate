## How

We ultilized matplotlib and seaborn to create boxplots, scatterplots, and distplots to depict the relationship between certain features and the code column (which we were trying to predict).

Below is a brief list of some of things that we learned about our features through EDA: 

1. Start speed has to be >= 60 mph generally to be a strike
2. End Speed has to be >= 60 mph generally to be a strike
3. Zone can be any value besides 10 for a strike to occur
4. Spin Rate is always >= 3500 for a strike to occur
5. All values for Spin Dir result in strike, does not appear to be super useful
6. -2 < px < 2 allows for a strike
7. -1 < pz < 5 allows for a strike

## Findings

Based on our EDA findings, we decided that the cols ["zone", "type_confidence", "pitch_type", "ab_id", "event_num", "y0", "type", "b_score", "outs", "pitch_num", "b_count", "s_count", "on_1b", "on_2b", "on_3b"] could be dropped due to their lack of correlation to the code column.
