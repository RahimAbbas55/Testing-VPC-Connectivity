<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Testing VPC Connectivity

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-connectivity)

**Author:** irahimsindhu@gmail.com  
**Email:** irahimsindhu@gmail.com

---

## Testing VPC Connectivity

![Image](http://learn.nextwork.org/affectionate_olive_majestic_marjoram/uploads/aws-networks-connectivity_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a service that lets you create a private, isolated network within AWS where you can launch and manage resources such as EC2 instances.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to to connect my public and private instance and connect my public instance with the internet.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the simplicity and clear concept details.

### This project took me...

This project took me 25 minutes to complete.

---

## Connecting to an EC2 Instance

"Connectivity means the ability of a user or system to establish a network connection with an EC2 instance and exchange data with it.

My first connectivity test was whether I could connect to my "Public EC2 Instance".

![Image](http://learn.nextwork.org/affectionate_olive_majestic_marjoram/uploads/aws-networks-connectivity_88727bef)

---

## EC2 Instance Connect

EC2 Instance Connect allows users to connect to an Amazon EC2 instance over SSH without manually managing long-term SSH key pairs. Instead, it uses AWS IAM permissions to control access and temporarily pushes a public SSH key to the instance when a connection is initiated.

My first attempt at getting direct access to my public server resulted in an error, because the security group associated to my public subnet had no inbound rules which allowed the traffic via the SSH. Once the new inbound rule was in place, the connection was established.

I fixed this error by introducing a new inbound rule which had the type set to SSH. Once this rule was applied, the instance recognized it and allowed the connection attempt via the SSH.

![Image](http://learn.nextwork.org/affectionate_olive_majestic_marjoram/uploads/aws-networks-connectivity_1cbb1b88)

---

## Connectivity Between Servers

Ping is a command-line tool that sends ICMP Echo Request packets to a target host and waits for a response. I used ping to test the connectivity between my local computer and the EC2 instance to verify that network communication was functioning correctly.

The ping command I ran was "ping 10.0.142.16"

The first ping returned "PING 10.0.142.16 (10.0.142.16) 56(84) bytes of data."
This meant that the host has sent data packets to the target but no response has been received.

![Image](http://learn.nextwork.org/affectionate_olive_majestic_marjoram/uploads/aws-networks-connectivity_defghijk)

---

## Troubleshooting Connectivity

I troubleshooted this by updating the inbound rules for my private subnet's security group by adding a new rule. This new rule allowed all the IPv4 ICMP messages.

![Image](http://learn.nextwork.org/affectionate_olive_majestic_marjoram/uploads/aws-networks-connectivity_4a9e8014)

---

## Connectivity to the Internet

Curl is a tool to test connectivity in a network. Curl is used to send data to or from a server

I used curl to test the connectivity between my public instance and the internet.

### Ping vs Curl

Ping checks whether a host is reachable over the network using ICMP packets, while curl sends requests to a specific URL or service (such as HTTP/HTTPS) and retrieves data from it.

---

## Connectivity to the Internet

I ran the curl command curl "https://learn.nextwork.org/projects/aws-host-a-website-on-s3" which returned heaps of data of the website to which I made the curl request.

![Image](http://learn.nextwork.org/affectionate_olive_majestic_marjoram/uploads/aws-networks-connectivity_8ee57662)

---

---
