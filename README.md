# Implementation-of-load-balancer-algorithms-in-network
Implementation of Load Balancer Algorithms in Networks

Implementation of effective load balancing algorithms that can optimize resource utilization, maximize throughput, minimize response time, and ensure high availability.

How Load Balancing Works :

A load balancer acts as a traffic cop, sitting between clients and backend servers. It intercepts incoming requests, evaluates the health and load of backend servers, and directs each request to the most appropriate server for processing. Load balancers use various algorithms to distribute traffic, such as round-robin, least connections etc.

Load Balancing Algorithms :

There are various load balancing algorithms that determine how traffic is distributed across backend servers. Some common algorithms include:

Round-robin : This is the simplest algorithm, which distributes traffic to servers in a sequential order.

Least connections : This algorithm directs traffic to the server with the fewest active connections.

Installation of NS2 (ns-2.35) in Ubuntu 20.04 LTS :

Step 1: Install the basic libraries like:

$] sudo apt install build-essential autoconf automake libxmu-dev

Step 2: Install gcc-4.8 and g++-4.8

Open the file using sudo mode

$] sudo nano /etc/apt/sources.list

Include the following line :

deb http://in.archive.ubuntu.com/ubuntu bionic main universe

$] sudo apt update

$] sudo apt install gcc-4.8 g++-4.8

Step 3: Unzip the ns2 packages to home folder:

$] tar zxvf ns-allinone-2.35.tar.gz

$] cd ns-allinone-2.35/ns-2.35

Modify the following make files.

~ns-2.35/Makefile.in

Change @CC@ to gcc-4.8

change @CXX@ to g++-4.8

~nam-1.15/Makefile.in

~xgraph-12.2/Makefile.in

~otcl-1.14/Makefile.in

Change in all places  @CC@ to gcc-4.8

Change in all places  @CPP@ or @CXX@ to g++-4.8

Open the file:

~ns-2.35/linkstate/ls.h

Change at the line no. 137

void eraseAll() { erase(baseMap::begin(), baseMap::end()); }

to this:

void eraseAll() { this-> erase(baseMap::begin(), baseMap::end()); }

Step 4: Open a new terminal and run the following commands:

$] cd ns-allinone-2.35/

$] ./install

Step 5: Set the PATH:

Open a new Terminal and run,

$] gedit .bashrc

Paste the following lines

export PATH=$PATH:/home/<yourusername>/ns-allinone-2.35/bin:/home/<yourusername>/ns-allinone-2.35/tcl8.5.10/unix:/home/<yourusername>/ns-allinone-2.35/tk8.5.10/unix

export LD_LIBRARY_PATH=/home/<yourusername>/ns-allinone-2.35/otcl-1.14:/home/<yourusername>/ns-allinone-2.35/lib

Note: Replace the <yourusername> with your linux user name

Run the following command:

$] source .bashrc

With this the environment is ready to use and implement this project
