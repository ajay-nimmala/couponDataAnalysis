AJAY NIMMALA – Coupon Data Analysis Read me file

CSV to a DataFrame:
Read the coupons data (in csv format) file and load it into a dataframe - data: Using Pandas’s read_csv method.

Overview of the data in the DataFrame:
After reading the data into a dataframe, understand the data using dataframe’s methods like
- data.info() – Provides basic information about the dataframe. More importantly, I was able to understand the basic data model, with the column names along with how many rows and columns are there in the dataframe.
- data.sample() – This helps in looking at actual sample of the data. This was very useful to understand some of the values of the data.
- data.columns – Sometimes because of the screen size, we will not be able to see all the columns, but this method will help us look at all the columns in the dataframe.

Clean Data (Null and Duplicate Values & Rename and Drop Columns):
After reviewing the data, clean null and duplicate records in the data, using the following methods.
- data.shape() – Gives the total number of rows and columns in the dataframe. It is good to know the baseline before cleaning the data.
- data.isnull().sum() – Gives the sum of null values in each of the columns. There were no null values in any of the user attributes columns. Validated the same by checking null values in a few columns.
o data.dropna() – To drop null values, if any
o data.loc[data['CarryAway'].isnull()].sample(5) – Check data with null values in ‘CarryAway’ column
- data.drop_duplicates(inplace = True) – Drop duplicates from the dataframe.
- Checked the shape of the dataFrame after clean up – Dropped about 74 rows of data.
- Finally, for practice and to make the data look more readable, replaced some of the values in columns like Time, Expiration, Passenger. Also, renamed the column ‘Y’ and ‘CouponAccepted’ to make it more meaningful.
- Created a new dataFrame (curated_data) from existing dataframe by dropping columns 'toCoupon_GEQ5min', 'toCoupon_GEQ5min', 'toCoupon_GEQ25min', which did not have a significance in the data analysis.











Analysis of Data:

What proportion of total observations chose to accept the coupon?
Mean value of the coupon accepted column will give us overall what is the percentage of total observation accepted the coupons. We found out that 56.75% of the total observations have accepted the coupon.

Continuing the analysis, did some plotting to understand coupon accepted for each of the features (columns)

1. Coupon Type – As we can see from the data that Carry out & Take Away coupons are the highest percentage of accepted coupons, followed by the restaurants coupons. Within restaurants as well, cheaper restaurants (<20) have higher acceptance rate. Coffee house coupons are most accepted from a volume POV, but their rejection rate is also equal (50-50). Following charts reflect the same based on data as well as in plotly’s density heatmap





Following plot reflects which coupon type has higher acceptance rate, pictorally. Its very clear from the picture that cheaper restaurants(<20) along with carry out and take away have higher percentage of coupon acceptance. Volume of coffee house coupons accepted is similar to that of cheaper restaurants and Carry out and Takeaway.







2. Education – Customers with “Some College – no degree” and who have a “Bachelors Degree” have higher volume along with ~60% acceptance rate.









3. Income – There is not a lot of huge variation of coupon acceptance rates based on income. All income ranges are trending between 48-60% acceptance rates. 





From the below chart, we can clearly see that customers who have an income between $62,500 and $99,999 do not accept coupons much.


Bar plots to visualize coupon acceptance based on user attributes:

Coupon Type – Restaurant(<20) and Carry out & Takeaway coupons have higher acceptance rates.


Gender – There is not a significant variation based on the gender of the driver.

Children – Drivers who have kids have a higher percent of coupon acceptance rates. 









Education Level – A different visualization of how education has an impact on coupon acceptance. All the data is for only customers who have accepted the coupon. Its very clear that customers with  “Some college – no Degree” and “Bachelors Degree” have higher coupons accepted.



Temperature & Weather– Its very clear that overall coupons are used/accepted on sunny days more than when the temperature is cooler. Its almost double on the days it is with higher temperature. Only significant coupon that is used during cooler days is for Carry out and take away.















Occupation – There are a lot of drivers in the profession of being a student or unemployed or in Computer & Mathematical profession. One observation here is that the drivers in this occupation tend to be using a lot of coffee coupons.




Age – Drivers who are between 20 and 30 years of age tend to be more receptive of a coupon.



Destination – Drivers who are not going to any urgent place are receptive of a coupon. Drivers who are going to either home or work are not very receptive.







Expiry – Drivers are more accepting of a coupon that has at least 24 hours than the ones that expire in 2 hours.



Marital Status – Customers who are either single (more) or have a married partner have higher percent usage than divorced and widowed. Even customers with an unmarried partner also have higher percent but not as much as single and married partners.



Passenger – Drivers who are driving without kids tend to use the coupon more than rejecting them but drivers who have friends with them have the higher acceptance rates. 







Time of the day – Higher percentage of coupons acceptance is during the day or early evening.  




Summary of Coupon Data analysis:
Data file has 12684 records of which 74 records were duplicates. After dropping the duplicates when I did my analysis of the data comparing the acceptance rate of drivers based on all the user attributes, following are my findings. You will my findings very similar to what I was able to showcase using charts in the above section. One thing to note is that I have not done analysis on the data based on multiple features at once, which we I have done only for coupon types ‘Bar’ and ‘Carry out & Take Away’.

Drivers with following features tend to accept a coupon than others:

- Destination - Drivers who are traveling to a non-urgent place.
- Passenger – If the passenger is a friend.
- Weather – If it is sunny.
- Temperature – High temperature.
- Time – During the day than early morning (7AM) or late night (10PM)
- Coupon – If the coupon type is ‘Carry Out & Take Away’ or Restaurant (<20)
- Expiration – If the expiry is 24hrs than under 2hrs.
- Gender – Not much difference between male or female drivers.
- Age – Drivers between ages 21 and 26.
- Marital Status – Single or having a married partner.
- Has Children – Drivers with no children have higher acceptance rates.
- Education – ‘Some college – No Degree’ and ‘Bachelors’ have higher acceptance rates.
- Annual Income – Drivers who make less than $62,500 and the ones who make more than $99,999.



Analysis on drivers who accepted the Bar Coupons:

- Drivers who got to the bar less than 3 times a month accept the coupon more (663) than the drivers who go more to the bar (153).
- Though there were ~40% of the coupons delivered to the drivers were accepted, Bar coupons are not the highest accepted coupons.
- Drivers who are less than 25 years of age and who go to the bar less than once a month tend to use the coupon more (532) than the other way round(292).
- From the general data analysis above - drivers who have "Some College - No Degree" or a "Bachelors Degree" tend to use the coupon more than others.


Analysis on drivers who accepted the Bar Coupons:

- Drivers who go out more than once (even more for drivers who go 4-8 times) use the Carry Away coupon more.
- Drivers who are driving alone or with Friends use the coupon more. Also drivers who are in the age range of 20-31 or over 50 use the coupon more than others.
- Drivers who are students, unemployed, computer & mathematics professionals tend to use Carry Away coupon more than others.
- Coupons are used on sunny days more than other days. When temperature is high.
- Coupons that expire in 24 hours are more preferable than coupons that expire in 2hrs.

