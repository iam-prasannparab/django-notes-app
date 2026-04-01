@Library("Shared") _
pipeline {
    agent {label "vinod"}
    
    stages{
        stage("Hello") {
            steps {
                script {
                    Hello()
                }
            }
        }
        stage("Code") {
            steps {
                script {
                    clone ("https://github.com/iam-prasannparab/django-notes-app.git","dev")
                }
            }
        }
        stage("Build") {
            steps {
                script {
                    docker_build("notes-app","latest","iamparab")
                }
            }
        }
        stage("Test") {
            steps {
                echo "This is testing"
            }
        }
        stage("Push") {
            steps {
                script {
                    docker_push("notes-app", "latest")
                }
            }
        }
        stage("Deploy") {
            steps {
                script {
                    docker_compose()
                }
            }
        }
        
    }
}
