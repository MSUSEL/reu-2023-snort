# reu-2023-snort
A repository to house the 2023 REU Snort project 

## Introduction
This project investigated network quality, specifically aspects separate from Quality of Service and performance. It uses Snort and Wireshark to record and detect potentially malicious packets between a containerized web server and the host machine to simulate traffic between microservice applications. 

## Tools
- Snort 3.1.63.0+
- Docker 24.0.4+
- Wireshark 3.6.2+

## Running
1. Download the file Dockerfile and the folder web-server into a directory and open a terminal window in this directory.
2. Add the video you wish to play to the html folder 
3. With Docker 24.0.4+ installed, run the command ***docker build -t webserver .*** (the final period is part of the command). This will take several seconds to run. 
4. 


## Network Quality tree 
1. The quality tree started with the highest node, microservice ecosystem quality
2. From there we branch out to the qualities of a microservice ecosystem, categorized in 8 additional nodes: functional stability, performance, compatibility, usability, security, and reliability, maintainability, and portability
3. Since our focus is security, we will solely expand on this node
4. We add a single node, network quality, beneath security
5. Network quality can be described in two ways: performance(Quality of Service) and communication
6. Since the focus of our project is to analyze network quality excluding quality of service, we'll only build more nodes under the communication node
7. Communication then splits up into two separate child nodes: benign and malware
8. Since Snort is not built to detect vulnerabilities in code, we focus on building child nodes from the malware node
9. This final step will give us the nodes necessary to define the way we can quantify network quality given that we're using Snort as our main tool
10. From malware we create two more child nodes: severity (priority of alerts) and frequency (number of alerts)













