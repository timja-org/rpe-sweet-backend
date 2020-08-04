pipeline {
   agent any

   stages {
      stage('Build') {
         steps {
            sh """
            rm -f *.xml
            wget https://gist.githubusercontent.com/timja/918722bbedaa0a76b50c8af2c2d3254e/raw/1bea98d9e6a570a52ef922fb0bc1b67c55ce0dc0/mix-of-junit-failures.xml
            """
        
            /*sh """
            export JAVA_HOME=/Users/timja/.sdkman/candidates/java/11.0.7.j9-adpt
            export PATH=${JAVA_HOME}/bin:${PATH}
            ./gradlew check
            """*/
         }

         post {
            success {
               junit '*.xml'
            }
         }
      }
      stage('Build-2') {
         steps {
            sh """
            rm -f *.xml
            wget https://raw.githubusercontent.com/jenkinsci/junit-plugin/master/src/test/resources/hudson/tasks/junit/junit-report-1233.xml
            """
        
            /*sh """
            export JAVA_HOME=/Users/timja/.sdkman/candidates/java/11.0.7.j9-adpt
            export PATH=${JAVA_HOME}/bin:${PATH}
            ./gradlew check
            """*/
         }

         post {
            success {
               junit '*.xml'
            }
         }
      }
   }
}
