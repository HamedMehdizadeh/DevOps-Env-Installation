# Configure GitLab pulgin on Jenkins
make sure you have already installed these plugins in the Jenkins

git_plugin
git_client_plugin
credentials
GitLab
gitlabAPI
gitlab_authentication

#### Prerequisites
1. Jenkins server
2. gitlab server

#### Install Git on Jenkins server
1. Install git packages on jenkins server
   ```sh
   yum install git -y
   ```

#### credential integration
1- in gitlab and in user setting --> access Token --> create new personal access token and make sure you just tik
the api checkbox and copy the access Token

2-now you go to creadential in jenkins GUI and add credentials --> select gitlab api token and paste your personal access Token and save it

3- in jenkins GUi first gitlab section fill the boxes like this
connection name : GitLab connection
gitlab host URL : https://gitlab.com
and in the credentials section use your personal access token credential and test the connection

4-go to jenkins server terminal and make ssh-keygen:
now go to the .ssh directory and read id_rsa.pub and copy
now go to gitlab GUI and profile setting section ---> ssh key ---> now paste your id_rsa.pub contain and add ssh key.

5- now go to jenkins server terminal and this time copy content of id_rsa file and copy.
go to jenkins GUI and credentials section and add credential --> now select ssh username with private key
and username will be git and paste your ssh private key and save the credentials

#### job setting

in each job setting you are going to configure
you need to use git as source code management
and fill the content like below :

repository URL : < copy and paste your project https url>
credential : <ssh username with private key id>

in the build trigers
please check this box :
build when a change is pushed to gitlab webhook url < your project url>
