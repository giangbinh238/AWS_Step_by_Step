# Part 1: Setting up the instance
## Create an instance 
Need to remember : 

Ubuntu Server 18.04 LTS (HVM), SSD Volume Type - ami-04b9e92b5572fa0d1 (64-bit x86) / ami-0bba96c31d87e65d9 (64-bit Arm)

Connect to Instant
Use this command 

`sudo apt-get update` 

 `sudo apt-get install python3-pip`
 
 `sudo apt install yum`
 
 `sudo apt-get install python3-pip`

`sudo pip3 install jupyter`
 
Make the jupyter remains always in the instance even we shut the computer terminal 

` nohup jupyter notebook --ip=0.0.0.0 &`

# Part 2 : Create Virtual Environment 
1. Use anaconda 

`curl -O https://repo.anaconda.com/archive/Anaconda3-2019.03-Linux-x86_64.sh`

`bash Anaconda3-2019.03-Linux-x86_64.sh`

IF conda command can't run : 

`export PATH=~/anaconda3/bin:$PATH`

Then create new environment

`conda activate <name>`

`conda install ipykernel`

`ipython kernel install --user --name=<name>`

Need Keras and Tensorflow to execute program :

`conda install keras`

`conda install opencv`

# Part 3 : Install web server 
By using apache 

Create new instance with SG :

 SSH 0.0.0.0 and HTTP 0.0.0.0

 Launch and use this code : 

 `sudo apt-get update`

 `sudo apt-get install apache2`

 `sudo apt-get install git`

 `git clone http:\\`

 `sudo mvsudo mv AWS_Tutorials/MNIST/index.html /var/www/html`

`sudo mv AWS_Tutorials/MNIST/static /var/www/html `
