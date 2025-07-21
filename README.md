<h1 align="center">TIC-TAC-TOE-GAME</h1>

Github-Actions Project:
https://mrcloudbook.com/github-actions-tic-tac-toe-game/#Step2A_Install_Docker_and_Run_Sonarqube_Container

https://github.com/Aj7Ay/TIC-TAC-TOE/tree/main
1. create ubuntu server

2.create IAM role to give administarator access

3. docker install on the server

sudo apt get update -y
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable
sudo systemctl status

docker ps -->permission denied
sudo usermod -aG docker ubuntu
newgrp docker
docker ps 
sudo chmod 777 /var/run/docker.sock

docker run -d --name sonar -p 9000:9000 sonarqube:lts-community

docker ps 

copy p.ip paste on browser

user: admin, pw: admin

sudo vi tools.sh

https://mrcloudbook.com/github-actions-tic-tac-toe-game/#Step2C_INSTALLATION_OF_OTHER_TOOLS

ll  -->here you see tools.sh file don't have execute permissions
chmod +x tools.sh 
./tools.sh

trivy --verson
kubectl version
java --version

git clone https://github.com/Aj7Ay/TIC-TAC-TOE.git

cd TIC-TAC-TOE
ls 
cd eks-terraform
change backend s3 bucket
terraform init  -->getting error

instance ki IAM role attatch cheyyali

terraform init 
terraform apply -auto-approve

goto sonar-qube dash board:
a. click manually--> name:TIC-Game-->main --> click setup--> click github actions

goto github repository --> click on settings--> click security tab & choose secrets and variables -->Actions -->new repository secret -->Name:SONAR_TOKEN, token: paste_Sonartoken-->add secret

same as above do it  sonar_host_url

after that goto sonar--> click on continue--> select other--> 2. see create a file sonar.properties in our repo

after that repo lo .github/workflows lo mana yaml file (sonar.yaml) create cheyyali...

click on actions to see here 

goto sonar qube dash board you can see scan our code 




