# Deploy Artifacts on a Tomcat Server
This configuration ensures that Jenkins automatically triggers a build when code is pushed to GitHub, and the resulting .war file is deployed to your Tomcat server.

## Setup CI/CD with GitHub, Jenkins, Maven & Tomcat.
• Setup Jenkins
• Setup & Configure Maven , Git.
• Setup Tomcat Server.
• Integrating GitHub,Maven ,Tomcat Server with Jenkins
• Create a CI and CD Job.
• Test the Deployment.

## Jenkins Stages:
To set up a Jenkins pipeline that performs the following actions:
**Checkout Code from GitHub**: Automatically triggers when a change is pushed to GitHub.
**Build with Maven**: Compiles and packages the code.
**Deploy on Tomcat**: Deploys the resulting .war file to a Tomcat server.

## Prerequisites

### Server Installation
- **Tomcat**: Tomcat should be installed and accessible from Jenkins. You can deploy using SCP, FTP, or direct file copying if Jenkins and Tomcat are on the same server.
- **Jenkins** : Jenkins should be installed and accessible.
- **Maven** : Maven should be installed and accessible from Jenkins

### Jenkins Plugin Installation and Setup
- **GitHub Integration**: Jenkins needs to be configured to trigger builds automatically when a change is pushed to the GitHub repository. This can be done using the GitHub Webhook.
- **Maven Integration**: Maven must be installed and configured in Jenkins.
- **Credentials**: Credentials for GitHub and Tomcat should be configured in Jenkins.
- **Pipeline: Stage View Plugin**: 
- **Pipeline: Utility Steps Plugin** : it provides the findFiles step.

## Set Environment Variables:
    ```
    GIT_REPO = 'https://github.com/your-repo.git'               // Replace with your GitHub repository URL
    BRANCH = 'main'                                             // Replace with the branch you want to build
    GIT_CREDENTIALS_ID = 'your-github-credentials'              // Replace with your GitHub credentials ID in Jenkins
    MVN_HOME='/opt/apache-maven-3.9.6'
    MAVEN_OPTS = '-Xms256m -Xmx512m'                            // JVM options for Maven
    TOMCAT_USER = 'your-tomcat-username'                        // Replace with your Tomcat username
    TOMCAT_PASSWORD = 'your-tomcat-password'                    // Replace with your Tomcat password
    TOMCAT_URL = 'http://your-tomcat-server:8080/manager/text'  // Replace with your Tomcat Manager URL
    ```