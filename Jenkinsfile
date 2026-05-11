pipeline {
agent any
stages {
 stage('Clone') {
 steps {
 git 'https://github.com/Charan304304/ci-node-app2.git'
 }
 }
 stage('Install Dependencies') {
 steps {
 bat 'npm install'
 }
 }
 stage('Run Application') {
 steps {
 bat 'node app.js'
 }
 }
 stage('Run Tests') {
 steps {
 bat 'npm test'
 }
 }
 stage('Build Docker Image') {
 steps {
 bat 'docker build -t ci-node-app2 .'
 }
 }
 stage('Run Docker Container') {
 steps {
 bat 'docker run -d -p 3000:3000 --name ci-container ci-node-app2'
 }
 }
}
}