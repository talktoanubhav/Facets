pipeline {
 agent none
 stages {
  stage('Build'){
   steps {
   dotnet build sample.txt
   }
  }
  stage('Stage'){
   steps {
   dotnet build sample.txt
   }
  }
 }
}