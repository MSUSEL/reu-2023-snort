# reu-2023-snort
A repository to house the 2023 REU Snort project 
Abraham Vega, Alyssa Ebeling, Isaac Greenwald
Mentor: Derek Reimanis 

Snort 3.1.65.0 installation (alyssa)
Network Quality Tree (abe and alyssa)


Docker installation
#uninstall conflicting packages
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
#
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg


