# reu-2023-snort
A repository to house the 2023 REU Snort project 

## Introduction
This project investigated network quality, specifically aspects separate from Quality of Service and performance. It uses Snort and Wireshark to record and detect potentially malicious packets between a containerized web server and the host machine to simulate traffic between microservice applications. 

## Tools
- Snort 3.1.63.0+
- Docker 24.0.4+
- Wireshark 3.6.2+

## Running

### Snort Configuration
1. After installing Snort 3.1.63.0 or a later version, install the community ruleset from the official Snort website.
2. Navigate to */usr/local/etc* and create a new directory called rules.
3. From the community ruleset, move the document titled *snort3-community.rules* into the new rules folder.
4. Using the command *touch local.rules*, create a document to use your own Snort rules. This can be used to test your Snort configuration and make sure it is working. 
5. By default, Snort configuration files should be located in */usr/local/etc/snort*. Navigate to this folder and open *snort_defaults.lua* in a text editor.
6. Set the variable $RULE_PATH to */usr/local/etc/rules/* for easy access to these files.
7. Open *snort.lua* in a text editor.
8. Set the variable $HOME_NET to the IP address of your computer on the docker0 network. This is typically *172.17.0.1*.
9. In section 5 under 'ips', add the lines *variables = default_variables,
                                            rules = [[
                                            include $RULE_PATH/snort3-community.rules
                                            include $RULE_PATH/local.rules
                                            ]]
11. In section 7, uncomment the line with text *alert_fast = {}*.
12. Between the brackets, add lines *file = true, packet = false, limit = 10,*.
13. Save and exit. Snort is now configured to log alerts. 

### Downloading Malware from Web-server
1. Download the file Dockerfile and the folder web-server into a directory and open a terminal window in this directory.
2. Rename the directory to Benign
3. Add the benign video you wish to play to the html folder 
4. With Docker 24.0.4+ installed, run the command ***docker build -t malware:SHA-256 .*** (the final period is part of the command) where SHA-256 is the id of the malware. This is to keep things organized when several containers are created. This will take several seconds to run. 
5. To begin the container, run the command ***docker run -d -p 8000:80 --name webserver malware:SHA-256***
6. In another terminal window, begin wireshark in packet sniffing mode with the command ***sudo wireshark***
7. From the wireshark GUI, select the docker0 network to monitor traffic from.
8. In a third terminal window, run the command ***sudo snort -c /usr/local/etc/snort/snort.lua -i docker0 -k none -A alert_fast -l /home/USERNAME***. This will monitor network traffic on the docker0 network and log any alerts to a document titled 'alert_fast.txt' located in your home directory in linux.
9. Open google chrome and go to **localhost:8000**
10. Click the "DOWNLOAD" button, which will download the malware from the container to localhost.
11. Stop the container, save the wireshark packet capture and stop Snort. The alert file for snort will be saved in the home directory, and if alerts are triggered they will appear in this document. 


## Network Quality tree 
1. The quality tree started with the highest node, microservice ecosystem quality
2. From there we branch out to the qualities of a microservice ecosystem, categorized in 8 additional nodes: functional stability, performance, compatibility, usability, security, reliability, maintainability, and portability
3. Since our focus is security, we will solely expand on this node
4. We add a single node, network quality, beneath security
5. Network quality can be described in two ways: performance(Quality of Service) and communication
6. Since the focus of our project is to analyze network quality excluding quality of service, we'll only build more nodes under the communication node
7. Communication then splits up into two separate child nodes: benign and malware
8. Since Snort is not built to detect vulnerabilities in code, we focus on building child nodes from the malware node
9. This final step will give us the nodes necessary to define the way we can quantify network quality given that we're using Snort as our main tool
10. From malware we create two more child nodes: severity (priority of alerts) and frequency (number of alerts)













