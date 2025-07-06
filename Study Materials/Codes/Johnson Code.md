Johnson Code is specifically used to create what are called Ring [[Counter]]s. The main idea behind them is that the counter and the table slowly fills up (either left to right or right to left) with log. 1 and then when full it starts to empty the counter in the same direction, overwriting the log. 1s with log. 0s.

#### Straight Ring Counter Example:

| **State** | **Q<sub>0</sub>**              | **Q<sub>1</sub>**              | **Q<sub>2</sub>**              | **Q<sub>3</sub>**              |
| --------- | ------------------------------ | ------------------------------ | ------------------------------ | ------------------------------ |
| 0         | <font color="#00b050">1        | 0         </font>              | 0                              | 0                              |
| 1         | 0                              | <font color="#00b050">1</font> | 0                              | 0                              |
| 2         | 0                              | 0                              | <font color="#00b050">1</font> | 0                              |
| 3         | 0                              | 0                              | 0                              | <font color="#00b050">1</font> |
| 0         | <font color="#00b050">1</font> | 0                              | 0                              | 0                              |
| 1         | 0                              | <font color="#00b050">1</font> | 0                              | 0                              |
| 2         | 0                              | 0                              | <font color="#00b050">1</font> | 0                              |
| 3         | 0                              | 0                              | 0                              | <font color="#00b050">1</font> |
| 0         | <font color="#00b050">1</font> | 0                              | 0                              | 0                              |
#### Johnson Code Counter Example:

| **State** | **Q<sub>0</sub>**       | **Q<sub>1</sub>**       | **Q<sub>2</sub>**       | **Q<sub>3</sub>**       |
| --------- | ----------------------- | ----------------------- | ----------------------- | ----------------------- |
| 0         | 0                       | 0                       | 0                       | 0                       |
| 1         | <font color="#00b050">1 | 0                       | 0                       | 0                       |
| 2         | <font color="#00b050">1 | <font color="#00b050">1 | 0                       | 0                       |
| 3         | <font color="#00b050">1 | <font color="#00b050">1 | <font color="#00b050">1 | 0                       |
| 4         | <font color="#00b050">1 | <font color="#00b050">1 | <font color="#00b050">1 | <font color="#00b050">1 |
| 5         | 0                       | <font color="#00b050">1 | <font color="#00b050">1 | <font color="#00b050">1 |
| 6         | 0                       | 0                       | <font color="#00b050">1 | <font color="#00b050">1 |
| 7         | 0                       | 0                       | 0                       | <font color="#00b050">1 |
| 0         | 0                       | 0                       | 0                       | 0                       |
