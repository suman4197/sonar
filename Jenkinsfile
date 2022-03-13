pipeline {
    agent any 
    environment {
        PATH = "$PATH:/usr/share/maven/bin" # should specufy the maven homen path
    }
    stages {
        stage ('cloning form git'){
            steps {
            git branch: 'main', url: 'https://github.com/suman4197/java-project.git'
            }
                
        }
        
        stage ('build stage') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage ('sonarqube analysis'){
            steps {
            withSonarQubeEnv('SonarQube 7.6'){   # name should be same as given in the configuration 
                sh 'mvn sonar:sonar'
            }
            }
            
        }
        
        
    }
}
