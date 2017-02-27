This is a simple and very useful Python script for network administrators to monitor the devices on a network by pinging every IP address on a subnet.

You need two Python modules - subprocess and ipaddress. The subprocess module lets you spawn new processes on which you run the ping command. The ipaddress module is used to define the network and to get the IP addresses that are available on that network.

At first, the program asks the user to input a network address using the CIDR notation (network address/prefix) format. A network is defined using this information and all available IP addresses in that network is obtained as a list.

The IP addresses are put through a loop and the ping command is executed using the popen constructor of subprocess module. The command output is parsed to check if it contains any of the strings "Destination host unreachable" or "Request timed out" and if found, that IP addresses is marked as offline otherwise it is online.

The ping command in this code limits the number of echo requests to 1 using the -n switch. If you want to run the program on Linux or Unix platform, replace -n with -c. To make the program run faster the timeout for ping response is set to a low value of 500 milliseconds.