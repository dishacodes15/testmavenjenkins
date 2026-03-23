​pipeline{
        agent any
        tools{
              maven 'maven'
             }
        stages{
              stage('Checkout'){
                  steps{
                        git branch: 'main', url: 'https://github.com/dishacodes15/testmavenjenkins.git'
                       }
                     }
  
       stage('Build') {
           steps {
               sh 'mvn clean package'  
           }
       }
 
       stage('Test') {
           steps {
               sh 'mvn test'  
           }
       }  
       stage('Run Application') {
           steps {
               sh 'java -jar target/mavenApp-1.0-SNAPSHOT.jar'
           }
       }       
   } 
   post {
       success {
           echo 'Build and deployment successful!'
       }
       failure {
           echo 'Build failed!'
       }
   }
}
