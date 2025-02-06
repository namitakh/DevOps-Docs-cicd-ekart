sudo apt-get update
sudo apt-get install wget apt-transport-https gnupg

#Add Trivy's GPG key:
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | gpg --dearmor | sudo tee /usr/share/keyrings/trivy.gpg > /dev/null

#Add the Trivy repository to your system's sources list:
echo "deb [signed-by=/usr/share/keyrings/trivy.gpg] https://aquasecurity.github.io/trivy-repo/deb generic main" | sudo tee -a /etc/apt/sources.list.d/trivy.list

sudo apt-get update

#install trivy
sudo apt-get install trivy
trivy --version
