pipeline { 
    agent any

options { timestamps() skipDefaultCheckout(true) }

stages {

stage('Checkout') { steps { checkout scm } }

stage('Verify Environment') { steps { bat 'java -version' bat 'mvn -version' } }

stage('Clean and Test') { steps { bat 'mvn clean test' } post { always { junit testResults: 'course-registration-app/target/surefire-reports/TEST-*.xml', allowEmptyResults: false } } }

stage('Package') { steps { bat 'mvn package' } }

stage('Archive Artifacts') { steps { archiveArtifacts artifacts: 'course-registration-app/target/*.jar', fingerprint: true } } }

post { success { echo 'Course Registration pipeline completed successfully.' } failure { echo 'Course Registration pipeline failed. Check the build and test logs.' } always { echo 'Pipeline execution finished.' } } }