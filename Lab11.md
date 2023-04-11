## Lab 11

- Name: Isabella Livingston
- Email: livingston.70@wright.edu

## Part 1 Answers

1. Hostname of the device: amnesia
2. MAC address of the NIC connected to the network: e4:5e:37:d1:b2:80 brd ff:ff:ff:ff:ff:ff
3. IP address: 130.108.104.23
4. Subnet mask: 255.0.0.0
5. Gateway address: 10.16.0.1
6. DHCP server address: 10.16.199.217
7. DNS server address: 130.0108.128.200
8. Public IP used for communications outside subnet: 130.108.104.23

## Part 2 Answers

1. `tcpdump` command:

   - How many packets were captured? 2037 packets were captured
   - Looking through the output, what traffic are you seeing? The output I'm seeing is a packet dump of my computer sending and getting packets from the AWS instance

2. Fancy `tcpdump` command: sudo tcpdump -i eth0 && host 8.8.8.8

3. Capturing `google.com` traffic:
   - Was there a difference in output from `curl` when using `http` or `https`? Yes, "http" printed a smaller piece of the website's code than with "https"
   - Was there a difference in packet content in `tcpdump` when using `http` or `https`? Yes, after running "https" I captured 5 packets. Also I captured 1 packet from running "http"
   - What caused the difference? I believe the reason why https produces more packets than http is because the packets were encrypted and needed to be processed more because of it
4. Save capture to a file: sudo tcpdump -w https_output.txt  'tcp[tcpflags] & (tcp-syn|tcp-fin) != 0'
   Read capture from a file: sudo tcpdump -r https_output.txt  'tcp[tcpflags] & (tcp-syn|tcp-fin) != 0'
   Don't forget to `commit` and `push` your capture to your `Lab11` folder.

## Part 3 Answers

1. Command(s) to install `python3` and `pip3`: sudo apt-get install python3, sudo apt-get install python3-pip
2. Run web server with `index.html` contents in your folder: 
3. Confirm content is being served:
   - Using `localhost`: ifconfig | grep "inet "
   - Using the system's private IP: ip a
   - Using the system's public IP: curl ipinfo.io
4. What's playing? Rick Astley - Never Gonna Give You Up
5. Command to show `LISTEN`ing processes: lsof | grep "python"
6. Command to `kill`: kill 3217
