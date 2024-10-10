5.1: Will the Customer Accept the Coupon?
<<<<<<< HEAD

1. Read in the `coupons.csv` file.
   
2. Investigate the dataset for missing or problematic data.
Study of dataset: dimentionality, type, zero-count

3. Investigate the dataset for missing or problematic data.
Study of dataset: dimentionality, type, zero-count

    3.1. 99.1% data from the "car" column is missing
        I decided not to use data from this column:

    3.2. Study series with a small amount of missing data (less than 1.71%) and save list of columns(column_w_missing) with missings.
                Column name: Bar found 107 NaN values - Uique values: ['never' 'less1' '1~3' 'gt8' nan '4~8']
                Column name: CoffeeHouse found 217 NaN values - Unique values: ['never' 'less1' '4~8' '1~3' 'gt8' nan]
                Column name: CarryAway found 151 NaN values - Unique values: [nan '4~8' '1~3' 'gt8' 'less1' 'never']
                Column name: RestaurantLessThan20 found 130 NaN values - Unique values: ['4~8' '1~3' 'less1' 'gt8' nan 'never']
                Column name: Restaurant20To50 found 189 NaN values - Unique values: ['1~3' 'less1' 'never' 'gt8' '4~8' nan]

    3.3. I decided to impute the missing values using mode (because the number of missing values is not significant - less than 1.7%)
                Filled missing values in 'Bar' with mode: never
                Filled missing values in 'CoffeeHouse' with mode: less1
                Filled missing values in 'CarryAway' with mode: 1~3
                Filled missing values in 'RestaurantLessThan20' with mode: 1~3
                Filled missing values in 'Restaurant20To50' with mode: less1

4. What proportion of the total observations chose to accept the coupon?
% drivers who accepted coupon out of the entire dataset
                ![alt text](image.png)
5. Use a bar plot to visualize the `coupon` column.
                ![alt text](image-1.png)
=======
1. Read in the `coupons.csv` file.
2. Investigate the dataset for missing or problematic data.
    Study of dataset: dimentionality, type, zero-count
    ![image](https://github.com/user-attachments/assets/dfa022dd-787a-4af8-99af-ba3c95644eec)
3. Decide what to do about your missing data -- drop, replace, other...

3.1. 99.1% data from the "car" column is missing

I decided not to use data from this column: data.drop('car', axis = 1)
3.2. Study series with a small amount of missing data (less than 1.71%) and save list of columns(column_w_missing) with missings.
      Column name: Bar
      Found 107 NaN values
      Unique values: ['never' 'less1' '1~3' 'gt8' nan '4~8']
      
      Column name: CoffeeHouse
      Found 217 NaN values
      Unique values: ['never' 'less1' '4~8' '1~3' 'gt8' nan]
      
      Column name: CarryAway
      Found 151 NaN values
      Unique values: [nan '4~8' '1~3' 'gt8' 'less1' 'never']
      
      Column name: RestaurantLessThan20
      Found 130 NaN values
      Unique values: ['4~8' '1~3' 'less1' 'gt8' nan 'never']
      
      Column name: Restaurant20To50
      Found 189 NaN values
      Unique values: ['1~3' 'less1' 'never' 'gt8' '4~8' nan]
3.3. I decided to impute the missing values using mode (because the number of missing values is not significant - less than 1.7%)
      Filled missing values in 'Bar' with mode: never
      Filled missing values in 'CoffeeHouse' with mode: less1
      Filled missing values in 'CarryAway' with mode: 1~3
      Filled missing values in 'RestaurantLessThan20' with mode: 1~3
      Filled missing values in 'Restaurant20To50' with mode: less1
4. What proportion of the total observations chose to accept the coupon?

% drivers who accepted coupon out of the entire dataset
      ![image](https://github.com/user-attachments/assets/db285f43-19c5-4bb6-b5d3-ad0c4bce9312)

5. Use a bar plot to visualize the `coupon` column.
      ![image](https://github.com/user-attachments/assets/9650a6c0-af67-47b8-9556-adf3942fc588)

5.a Another way to visualize the coupon column:

     ![image](https://github.com/user-attachments/assets/7259cd50-8043-424b-affd-3eef04030fd0)

6. Use a histogram to visualize the temperature column.
        ![image](https://github.com/user-attachments/assets/f27ff67b-d33b-49b4-b264-e3ca0caba053)

**Investigating the Bar Coupons**

Now, we will lead you through an exploration of just the bar related coupons.  

1. Create a new `DataFrame` that contains just the bar coupons.
        ![image](https://github.com/user-attachments/assets/165eff6b-370e-4b61-b5bd-4e4d583893cf)

2. What proportion of bar coupons were accepted?
        ![image](https://github.com/user-attachments/assets/08fdb7ba-d639-4e3c-a4a7-7428e34ccb0f)

3. Compare the acceptance rate between those who went to a bar 3 or fewer times a month to those who went more.
        ![image](https://github.com/user-attachments/assets/8b87c31a-3c66-4a67-a0d3-d4ccc726b27d)

4. Compare the acceptance rate between drivers who go to a bar more than once a month and are over the age of 25 to the all others.  Is there a difference?
        ![image](https://github.com/user-attachments/assets/4c1c325e-c087-42fa-be6f-e14a7a010f5e)

5. Use the same process to compare the acceptance rate between drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry.
        ![image](https://github.com/user-attachments/assets/f110aa3c-2f77-42b8-a405-7c43150ee617)

6. Compare the acceptance rates between those drivers who:

- go to bars more than once a month, had passengers that were not a kid, and were not widowed *OR*
- go to bars more than once a month and are under the age of 30 *OR*
- go to cheap restaurants more than 4 times a month and income is less than 50K.
        ![image](https://github.com/user-attachments/assets/dea66682-73f1-4bfa-8ee7-ad8af1381a0d)

7.  Based on these observations, what do you hypothesize about drivers who accepted the bar coupons?
        Drivers who are most likely accept coupon are: 
     1) Drivers without kid's passanger(s) 
     2) Drivers who are 25 - 30 years old 
     3) Drivers who visit the bar more than once a month  

### Independent Investigation

Using the bar coupon example as motivation, you are to explore one of the other coupon groups and try to determine the characteristics of passengers who accept the coupons.  
![image](https://github.com/user-attachments/assets/11e398a1-417b-439c-b45c-caf9866145b6)
Let's explore the Carry out and Take away group - it has the highest percentage of coupon acceptance.
![image](https://github.com/user-attachments/assets/aee50a94-6c7e-4cca-990d-533ac73e278f)

Bar plot - Passanger column vs coupon Acceptance
![image](https://github.com/user-attachments/assets/4b5e7591-0815-4cc7-9535-52c859ba0a34)
Drivers without passangers most likely accept coupon Carry out and Take Away

Cross-tabulation function shows how many times each combination of 'Age' and 'Y' occur.
![image](https://github.com/user-attachments/assets/ce36ec31-8878-4698-a151-6d4a60b538f0)
Age vs Carry out and take Away shows what most likely couopon Accept people with age 50plus.

Acceptance rate between those who went to a Carry Out and Take Away 3 or fewer times a month to those who went more 3 times
![image](https://github.com/user-attachments/assets/6fc3bf11-ee19-42de-aec0-56212ec15a13)
>>>>>>> bc31df8bc7448e9649d4d66fc2ae18970d2b7481
