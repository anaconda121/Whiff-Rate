At first, we tried modeling with regression instead of classification, so we converted the code column to code_num and mapped each code to a number between 0 and 1. Numbers closer to 1 were better for the pitcher while numbers closer to 0 were better for the batter. This came with a few problems, such as large class imbalances and a lack of a rounding cutoff map. There were also too many other variables (baseball-wise) that could influence the outcomes of pitches. The accuracy of our models was extremely low as a result. Thus, we switched to a simpler binary classification problem.

We cut all pitches from the dataset except for swinging strikes and foul balls in 2-strike counts. Typically, pitchers want to strike out batters in 2-strike counts, so they try throwing pitches with certain qualities (eg. harder fastballs, curveballs with more break, pitches on the corners of the strikezone) that make them harder to touch. Our goal narrowed down to modeling these qualities. 
To solve the imbalance problem, we simply trimmed the number of foul balls to equal the number of strikes. In decreasing the dataset's size, this also greatly sped up the models' training times.

Also, using rudimentary baseball knowledge and EDA we trimmed 15 columns. These included meta information about the state, such as the batting team's score; columns that merely summarized information in other columns (thus being correlated to them), such as pitch_type; and 'zone', which we couldn't tell the meaning of and and didn't seem related to code during EDA.

We split our dataset into a training, testing, and final validation set. The testing set had 0.3 size of the training set and the validation set had 0.3 size of the testing set.

We normalized features afterwards to increase performance of our MLP, then tested our other models on the normalized features (called 'scaled' in the code) to see which ones were affected. The MLP received the only significant accuracy increase (about 8%), and the only other change was faster training for the AdaBoost model (from 524 to 268 seconds).

Finally, to measure ROC_AUC score with sklearn, we had to convert code from S/F to 1's and 0's. 
