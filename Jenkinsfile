pipeline{
agent any

        stages{




			    stage('Build docker image'){
                             steps{
                                 script{
                                    sh 'docker build -t hajerbenyahia/angularproject .'
                                 }
                             }
                         }




      stage('Docker login') {

                                         steps {
                                          sh 'echo "login Docker ...."'
                   	sh 'docker login -u hajerbenyahia -p hajer1234'
                               }  }
		 stage('Docker push') {

                 steps {
                      sh 'echo "Docker is pushing ...."'
                     	sh 'docker push hajerbenyahia/angularproject'
                        }  }

                        stage('Docker compose') {

                          steps {
                               sh 'docker-compose up -d'
                                 }  }
          /* stage('Clean')
           {
            
            steps {

                sh 'docker image rmi hajerbenyahia/angularproject'
           
                 
            }
         
         
         } */
         
         
         }


        }
post {
                                                success {
                                                     mail to: "hajer.benyahia@polytechnicien.tn",
                                                     subject: "Hajer BEN YAHIA's Pipeline Success",
                                                     body: "success on job ${env.JOB_NAME}, Build Number: ${env.BUILD_NUMBER}, Build URL: ${env.BUILD_URL}"
                                                }
                    failure {
                        mail to: "hajer.benyahia@polytechnicien.tn",
                         subject: "Hajer BEN YAHIA's Pipeline Failure!",
                         body: "Failure on job ${env.JOB_NAME}, Build Number: ${env.BUILD_NUMBER}, Build URL: ${env.BUILD_URL} "
                    }
}
      }
