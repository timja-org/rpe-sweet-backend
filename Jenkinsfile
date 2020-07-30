pipeline {
   agent any

   stages {
      stage('Build') {
         steps {
            // Get some code from a GitHub repository
        

            // Run Maven on a Unix agent.
            sh """
            sdk use java 11.0.7.j9-adpt
            ./gradlew check
            """
         }

         post {
            // If Maven was able to run the tests, even if some of the test
            // failed, record the test results and archive the jar file.
            success {
               junit '**/build/test-results/TEST-*.xml'
               archiveArtifacts 'build/libs/*.jar'
            }
         }
      }
   }
}
