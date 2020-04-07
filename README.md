# selenium_docker_jenkins_runner

To Run tests Create a Pipeline project in jenkins
Jenkinsfile ->
1) Up the Dockerized Selenium Grid
2) Run the test using automation_service by using the Image from docker hub 
(Image creation part covered in `https://github.com/ayushvipinjain/selenium_docker_jenkins`)
3) Post the Artifacts/Automation Reports)
4) Down the Selenium Grid


Note - > Removed Ports from the docker-compose when running on CI because in case of running Job Simultaneosly you may encounter port already in use error.

