pipeline {

    agent any


    tools {

        // Install the Maven version configured as "M398" and add it to the path.

        maven "M398"

    }


    stages {

        stage('Echo Version') {

            steps {

                sh 'echo Print Maven Version'

                sh 'mvn -version'

            }

        }

        stage('Build') {

            steps {

                // Get some code from a Gitea repository specifying the main branch

                git branch: 'main', url: 'https://github.com/OrgYT/Jenkins-repo1.git'

                // Run Maven Package command and skip tests

                sh 'mvn clean package -DskipTests=true'

            }

        }

        stage('Unit Test') {

            steps {

                sh 'mvn test'

            }

        }

    }

}
 
