# Greedy algorithms and dynamic programming

### Task Description

In the notes, we discussed an example of breaking down a sum into coins. We have a set of coins `[50, 25, 10, 5, 2, 1]`. Imagine you are developing a system for a cash register that needs to determine the optimal way to give change to a customer.

You need to write two functions for the cash register system that dispenses change to the customer:

1. Greedy Algorithm Function: find_coins_greedy
   This function should take an amount to be given as change and return a dictionary with the number of coins of each denomination used to make up that amount. For example, for an amount of 113, this would be the dictionary `{50: 2, 10: 1, 2: 1, 1: 1}`. The algorithm should be greedy, meaning it should first choose the largest available denominations of coins.

2. Dynamic Programming Function: find_min_coins
   This function should also take an amount for change but use dynamic programming to find the minimum number of coins needed to make up that amount. The function should return a dictionary with the denominations of coins and their quantities to achieve the given amount in the most efficient way. For example, for an amount of 113, this would be the dictionary `{1: 1, 2: 1, 10: 1, 50: 2}`.

Compare the efficiency of the greedy algorithm and the dynamic programming algorithm based on their execution time or Big-O notation, and consider their performance with large amounts. Highlight how they handle large sums and why one algorithm might be more efficient than the other in certain situations. Add your conclusions to the readme.md file of the homework assignment.

### Результати тестування алгоритмів

|   Amount |   Функція жадібного алгоритму (s) |   Функція динамічного програмування (s) |
|---------:|:---------------------------------:|:---------------------------------------:|     
|       10 |                        0.00044720 |                              0.00774380 |     
|       55 |                        0.00054610 |                              0.05264310 |     
|      113 |                        0.00193090 |                              0.10950590 |     
|      207 |                        0.00058790 |                              0.20413600 |     
|      505 |                        0.00054430 |                              0.63495490 |     
|     1001 |                        0.00053840 |                              1.38917250 |     

### 1. Жадібний алгоритм

- Жадібний алгоритм вибирає монети найбільшого номіналу до повного розподілення суми.
- Кожна монета перевіряється один раз: O(n), де n — кількість монет у наборі.
- Складність залежить від швидкості розподілення суми найбільшими монетами.

### 2. Алгоритм динамічного програмування

- Цей алгоритм використовує таблицю для зберігання мінімальної кількості монет для кожної можливої суми до заданої суми.
- Ініціалізація таблиці: O(m), де m — сума для розподілу.
- Оновлення таблиці для кожної монети і суми: O(c \* m), де c — кількість монет, m — сума.
- Таким чином, загальна часова складність становить O(c \* m).

#### Висновки:

1. Жадібний алгоритм працює швидше, але не завжди дає оптимальний результат.

2. Алгоритм динамічного програмування завжди знаходить оптимальний результат, але вимагає більше часу і пам'яті.