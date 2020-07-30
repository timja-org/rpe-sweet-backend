pipeline {
   agent any

   stages {
      stage('Build') {
         steps {
            sh """
            export JAVA_HOME=/Users/timja/.sdkman/candidates/java/11.0.7.j9-adpt
            export PATH=${JAVA_HOME}/bin:${PATH}
            ./gradlew check
            """
         }

         post {
            success {
               junit '**/build/test-results/TEST-*.xml'
               archiveArtifacts 'build/libs/*.jar'
            }
         }
      }
   }
}
