# Analyzing Big Data with SQL
## 📝 Assignment Objective
Imagine that you have been hired as a data analyst for a company that plans to disrupt the airline industry by building an underground high-speed passenger rail tunnel.
The company needs your help to decide which two major United States airports this tunnel should connect. 
The distance between the airports must be within a specified range, and the airports must have a large volume of air travelers flying between them in both directions. The company believes that these air travelers can be persuaded to switch to
high-speed rail because of frustratingly long flight delays.

You must write a SQL statement and analyze the result to recommend which two airports this rail tunnel should connect. 

Recommend which pair of United States airports should be connected with a high-speed passenger rail tunnel. To do this, write and run a 
SELECT statement to return pairs of airports that meet the criteria below:
* Between 300 and 400 miles apart and that had at least 5,000 (five thousand) flights per year on average in each direction between them. 
* Arrange the rows to identify which one of these pairs of airports has largest total number of seats on the planes that flew between them. 
* The company is also interested to know the average arrival delay for flights between these two airports.

## 🛠️ Method
I identified this route by running the following SELECT statement using **Impala**:
            'SELECT flights.origin
              ,flights.dest
              ,round(AVG(flights.distance / 10)) AS avg_distance
              ,round(COUNT(flights.flight / 10)) AS flights_per_year
              ,round(SUM(planes.seats / 10)) AS number_of_plane_seats
              ,round(AVG(flights.arr_delay)) AS avg_delay_time
            FROM flights
            LEFT JOIN planes ON flights.tailnum = planes.tailnum
            WHERE distance >= 300
              AND distance <= 500
            GROUP BY flights.origin
              ,flights.dest
            HAVING flights_per_year >= 5000
            ORDER BY number_of_plane_seats DESC LIMIT 10;'

 ## 🚀 Recommendation
 I recommend the following tunnel route:
 	||First Direction|	Second Direction|
  |-|--------------|------------------|
|Three-letter airport code for origin|	SFO	|LAX|
|Three-letter airport code for destination|	LAX|	SFO|
|Average flight distance in miles|	337	|337|
|Average number of flights per year|	14712|	14540|
|Average annual passenger capacity|	1996597|	1981058|
|Average arrival delay in minutes|	10|	14|


