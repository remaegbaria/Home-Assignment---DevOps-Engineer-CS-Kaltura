# Home Assignment-Jenkins

this code get a name and two ports from the user and run Apache HTTP Server image that serve on the two ports the index.html page that will contain the input name and the current date and time.

## Installation

first in your Jenkins server install docker.

```bash
sudo apt install docker.io
```
open the Jenkins to create a new item with multibranch pipeline 
and go to the Branch Sources and select GitHub then paste the repository URL to Repository HTTPS URL field , make sure that Build Configuration is by Jenkinsfile

## To run

go to build with parameters and insert the three parameters fields
then select build and you can view outputs by selecting Console output

## View the html file

open the browser and enter URL that contain your instance Public IPv4 address and one of the ports inputs in this way:

```bash
Public IPv4 address:port
```


## Receive status in slack

after the build process is done a build status sent to the devops-engineer channel in my slack account (see the print-screen-slack-notifications.png file)
