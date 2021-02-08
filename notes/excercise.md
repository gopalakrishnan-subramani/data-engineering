
 touch employees.csv
 
 John,Male
 Mary,Female
 
read the csv using sc.textFile(...)
split the line using comma ,

rdd1 = make a tuple with name and gender (John,Male)

--

touch salary.csv

John,4000
Marry,6000

read the csv using sc.textFile(...)
split the line using comma ,

rdd2 = make a tuple with name and salary (John,4000)

--

then join rdd1 with rdd2

the expected output should be 


(John, (Male, 4000))
(Mary, (Female, 6000))
