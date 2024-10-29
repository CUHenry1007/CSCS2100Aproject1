# CSCI2100A Project 1

Name:	Yeung Paak Hang

SID:	1155213281

**It is a Project using C++ language.**

![image](https://github.com/CUHenry1007/CSCS2100Aproject1/blob/dced9dae32abc3628f0a75eebad7003a9c63829d/STAT.png)

## Guideline

### Step1: Run the Program

My program is call **Project1.cpp**. Assume TA have finished the setup in the Setup guideline from TA. The following steps is compiled by **windows**.

```batch
g++ --version
g++ Project1.cpp -o code -lcurl -Wl,-Bstatic
set API_KEY=YOUR_API_KEY
code.exe
```


### Step2: Return the output file

After compiled and run the program, waiting around 1 to 2 minutes, the 4 output file will be returned in .csv format: 

table1.csv,
table1_sorted_a.csv,
table1_sorted_b.csv,
table2.csv:

![image](https://github.com/user-attachments/assets/5dcc51eb-7ed7-4b94-a013-968da7ca9159)


## Explaination of the output file

The stock ticket follows the order on P.2 of the specifications at the begining (Without sorting).

![image](https://github.com/user-attachments/assets/edf04552-c4b8-4e76-9889-ff1f7b7e68c3)


### 1st outputed file: table2.csv

The first outputed file will be table2.csv. It contains the id, ticketr, and 5 year historical data (I have picked data from 2019-10-10 to 2024-10-10) in 1 cell.

To generate the output, first I made some change of the function historical_market_cap_api(), shown as below:

![image](https://github.com/user-attachments/assets/6ddb1700-8ce3-487b-ac23-76a095627e51)

The details of the code has been commented, the main idea is to take the required data to form a formatted output string and return it. Then, in the main() function, it will create table2.csv file, and input the id (using value of i), tickers (using stocks[30], without sorting), and call the function historical_market_cap_api() to return data for 30 times.

![image](https://github.com/user-attachments/assets/9de479b4-fa1a-45e3-8205-99ed7455ca1b)

As the file size too large, I use excel to show the output:

![image](https://github.com/user-attachments/assets/ed46fa89-ec5d-43b9-9ed7-b9b5acfd6506)


### 2nd outputed file: table1.csv

The second outputed file will be table1.csv. It contains the tickers, market_cap, pointer.

To generate the output, first I made some change of the function market_cap_api(), shown as below:

![image](https://github.com/user-attachments/assets/efa6c37f-12c3-42d6-a9d8-7dd8098a7b19)

The details of the code has been commented, the main idea is to take the required data to form a formatted output string and return it. Then, in the main() function, it will create table1.csv file, and input the tickers (using stocks[30], without sorting), call the function historical_market_cap_api() to return market_cap, and pointer (using i) for 30 times.

![image](https://github.com/user-attachments/assets/0b54f4f2-bbff-4733-899f-d150a2bacb7e)

Output file:

![image](https://github.com/user-attachments/assets/3702a625-afed-44d6-acf3-f39e4bc0234f)


### 3rd and 4th outputed file: table1_sorted_a.csv and table1_sorted_b.csv

The third and last outputed file will be table1_sorted_a.csv and table1_sorted_b.csv.. They are similar to table1.csv, the difference is the data ordered by the tickers in lexicographical order and ordered by the market cap in ascending order.

To generate the output, first I made two function of quicksort: quickSort() and pivot(). The reason of using quicksort has answered on the report and the details of the code has been commented.

Then, in the main() function, using quicksort function to sorted the tickers in lexicographical order. Next, read the table1.csv (we just created) and take the data out, in order to know the value of pointer for the corresponding tickers.

Finally, create table1_sorted_a.csv file, and input the tickers (using stocks[30], after sorting), the corresponding market cap and pointer for 30 times.

![image](https://github.com/user-attachments/assets/df5b006c-6ff6-4f0f-857b-b574f25b4737)

Output file (table1_sorted_a.csv):

![image](https://github.com/user-attachments/assets/f7ddf6cc-3d4f-4190-bf6b-a767d25fea01)

For table1_sorted_b.csv, in the main() function, using quicksort function to sorted the market cap in ascending order.Then, create table1_sorted_b.csv file, and input the tickers (using stocks[30], after sorting), the corresponding market cap and pointer for 30 times.

![image](https://github.com/user-attachments/assets/7a59c807-a56d-4e0b-81a5-1e5f6ae015dd)


Output file (table1_sorted_b.csv):

![image](https://github.com/user-attachments/assets/f482a76c-ef17-48bc-b914-c751e716d483)




