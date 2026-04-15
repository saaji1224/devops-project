# devops-project
# CI CD: 
* `Continous Integartion` is nothing but combination of both build and test happen at the same time.
* Will compile the code it will perform the unit test and pack the source code and it install dependencies.
* Whenever a developer commits the code using source code management like Git, then the CI pipeline get the chnages of the runs automatically build and unit test.
    * Due to integarting new code with old code, we can easly get to know the code is a success or fail.
    * It finds the error more quickly.
    * Delivery the products to client more frequently.
    * Developers don't need manual tasks.
    * Reduces the deveopler time 20% to 30%
* `Continous Delivery` : It is making it available for deploymnet. Anytime new build artifcat is available, the artifact is automatically placed in the desired environment and deployed.
* `Continous Deployment` : It is when you commit your code then gets automatically tested,build and deploy on the `production` server.
* `Plugin` : Plugins are small softwares that are used to perform some actions and it is used to provide some extra features on our jenkins dash board
<img width="872" height="485" alt="image" src="https://github.com/user-attachments/assets/799a6a5d-4bfe-4927-a398-a14591a81ae6" />
<img width="792" height="374" alt="image" src="https://github.com/user-attachments/assets/a3f2dfcc-748c-4044-9f00-f984d781a573" />
<img width="710" height="348" alt="image" src="https://github.com/user-attachments/assets/c88b2cbc-95ff-4967-bdd5-d86f3754510b" />

* Lunch one ubuntu Instance
```
vi jenkins.sh
#!/bin/bash
set -e
sudo apt update -y
sudo apt upgrade -y
sudo apt install -y openjdk-17-jdk
java -version
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins -y
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins

# check the passwd
cat /var/lib/jenkins/secrets/initialAdminPassword

# jenkins workspace directory
/var/lib/jenkins/workspace
```
* Webhook configuration: Whenever developer commit and push the changes at that time automatically build the jenkins job.
* goto github repo settings --> webhook --> Add webhook --> payload url : jenkins_url/github-webhook/ --> content type: Json --> Add webhook
* In jenkins job configure -- need to select GitHub webhook trigger for GitSCM polling








  
