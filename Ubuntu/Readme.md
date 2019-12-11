# Create an instance 
Need to remember : 
Ubuntu Server 18.04 LTS (HVM), SSD Volume Type - ami-04b9e92b5572fa0d1 (64-bit x86) / ami-0bba96c31d87e65d9 (64-bit Arm)
Connect to Instant
Use this command 

`sudo apt-get update` 

 `sudo apt-get install python3`
 
 `sudo apt install yum`
 
 `sudo apt-get install python3-pip`

Make the jupyter remains always in the instance even we shut the computer terminal 

` nohup jupyter notebook --ip=0.0.0.0 &`
