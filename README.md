# Cluster-Based-Map-For-Ship-Tracking
Name: Luv Arora   
Roll No: 2021003 

Division: A

Dept: Computer Engg

# **Step 1**: Install Redis Database (link: https://redis.io/download )

I used ubuntu 18.04 LTS cmd prompt on Windows(download from microsoft store) and executed the following commands to launch my redis server

![image](https://user-images.githubusercontent.com/81869471/115849322-65f0aa80-a442-11eb-97b0-4f452d7cc5ce.png)

# **Step 2**: Launch the Redis Client:

$ redis-cli

You can check its response using PING command

# **Step 3**: Adding ships data

To Track the ship we have to add Ships location along with its unique id in our database using:

![image](https://user-images.githubusercontent.com/81869471/115852178-6c345600-a445-11eb-91fc-00cb43814266.png)

# **Step 4**: Unique Hash Value is created

Once data is loaded for the System to identify it, a Hash is created which has the key, latitude and longitude and the unique id (MMSI)

![image](https://user-images.githubusercontent.com/81869471/115852416-b0275b00-a445-11eb-9c77-183c3619374e.png)

Note:
I have provided data in G2 and G3 excel sheet. It has complex data as well as minimised data.
What we require for representation of ship is latitude, longitude, mmsi and hash value.

# **Step 5**: Sorting required data

Once ships location is added in the database and geohash value is is obtained, copy this data is a new excel file.
The only data required is - latitude, longitude , mmsi and geo hash.
As soon as step 4 is performed for all ships, add those geohashes into the excel file.

I have added the data in the GEO DATA excel file.(perform step 3 and step 4 for any number of ships that you want to represent on the system) 

# **Step 6**: Representation of the Final Data

The only file required now is GEO DATA which has latitude, longitude, mmsi and geo hash.

To represent the data i have used Tableau 2021.1 (Download link:https://www.tableau.com/products/desktop/download)

It is simple process for installation. You can refer to this video for installation of tableau - https://www.youtube.com/watch?v=U5Jt2psRXXQ

To connect our data with tableau we need to install Cdata ODBC Drivers (link:https://www.cdata.com/drivers/redis/odbc)

These drivers are used to connect our redis database with tableau but as we are using filtered data we can directly connect tableau with out excel file(GEODATA.xlsx)

We can connect our excel file as shown below:

![image](https://user-images.githubusercontent.com/81869471/115988693-7dfa3280-a5d8-11eb-96c2-2f5c6609b17d.png)

Once connected it will open the data source tab where we need to drang and drop our excel sheet
The data will be listed in form of a table:

![Capture1](https://user-images.githubusercontent.com/81869471/115989009-b6e6d700-a5d9-11eb-878f-bbe06ae5cd74.PNG)

Now we put the data on to a sheet to display it :

![image](https://user-images.githubusercontent.com/81869471/116189937-5bd2f280-a747-11eb-8ce6-369a8c237c0a.png)

The above image shows smoe of the ships individually, so now we convert it into a cluster by grouping them in a radius of 50 km:

![1](https://user-images.githubusercontent.com/81869471/116190160-c08e4d00-a747-11eb-9f4c-475f9bec8d23.png)

Right and click on group data to create a cluster:

![2](https://user-images.githubusercontent.com/81869471/116190269-f29faf00-a747-11eb-9e76-e1e26a7efe40.png)

Finally a cluster is created in a form of MMSI group. The base station now can easily identify the group of ships which require more attention by just checking how many ships are present in the ship cluster . Using tableau we can even give clour to such clusters to represent which clusters have more amount of ships.

# CONCLUSION:
We have stored, processed and retrieved ship position sent by AIS using Redis. The cluster point is used to determine the center point of the clustered ships. Then the result ship position query is plotted into the web based map using Tableau. The data requested by the first user is kept in the memory so reading and writing activity shall be faster. Redis is a memory based cache, the data is first kept in the memory so writing and reading activity is faster



