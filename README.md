# Home Assignment-Jenkins

this code get a name and two ports from the user and run Apache HTTP Server image that serve on the two ports the index.html page that will contain the input name and the current date and time.

## Required
Jenkins server and plugins to install in Jenkins

#### Install Docker

first install docker in your Jenkins server.

```bash
sudo apt install docker.io
```

#### Install docker plugins in Jenkins

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/docker%20plugins.png)

#### Install slack notifications plugin

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/slack%20plugin.png)

open the Jenkins to create a new item with multibranch pipeline 

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/new%20item.png)

in Branch Sources select GitHub 

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/github%20connection.png)

paste the repository URL to Repository HTTPS URL field

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/gitub%20repo.png)

make sure that Build Configuration is by Jenkinsfile

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/build%20config%20jenkinsfile.png)

## To run

go to build with parameters and insert the three parameters fields then select build

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/build%20project.png)

you can view outputs by selecting Console output

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/console%20output.png)

## View the html file

open the browser and enter URL that contain your instance Public IPv4 address or localhost in case that you work in local computer then add one of the ports inputs in this way:

```bash
Public IPv4 address:port
or
localhost:port
```

#### you must see this

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/html%20page.png)

## Receive status in slack

after the build process is done a build status sent to the devops-engineer channel in my slack account

![image](https://github.com/remaegbaria/Home-Assignment---DevOps-Engineer-CS-Kaltura/blob/main/screenshots/print-screen-slack-notifications.png)
