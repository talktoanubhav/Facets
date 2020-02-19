pipeline {
 agent any
 stages {
  stage('Build'){
   dotnet build sample.txt
  }
  stage('Stage'){
   dotnet build sample.txt
  }
 }
}