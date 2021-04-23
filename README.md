# Cluster-Based-Map-For-Ship-Tracking
Name: Luv Arora   
Roll No: 2021003 

Division: A

Dept: Computer Engg

Step 1: Install Redis Database (link: https://redis.io/download )

I used ubuntu 18.04 LTS cmd prompt on Windows(download from microsoft store) and executed the following commands to launch my redis server

![image](https://user-images.githubusercontent.com/81869471/115849322-65f0aa80-a442-11eb-97b0-4f452d7cc5ce.png)

Step 2: Launch the Redis Client:

$ redis-cli

You can check its response using PING command

To Track the ship we have to add Ships location along with its unique id in our database using:

![image](https://user-images.githubusercontent.com/81869471/115852178-6c345600-a445-11eb-91fc-00cb43814266.png)

Once data is loaded for the System to identify it, a Hash is created which has the key, latitude and longitude and the unique id (MMSI)

![image](https://user-images.githubusercontent.com/81869471/115852416-b0275b00-a445-11eb-9c77-183c3619374e.png)
