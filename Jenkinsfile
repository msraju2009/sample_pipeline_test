pipeline {
  agent any
  stages {
    stage('Maven Build') {
      parallel {
        stage('Maven Build') {
          steps {
            echo 'From Maven build'
          }
        }

        stage('Static Code Analysis') {
          steps {
            echo 'From static code analysis using SonarQube'
          }
        }

      }
    }

    stage('Deploy WAR ') {
      parallel {
        stage('Deploy WAR ') {
          steps {
            echo 'Deploy WAR file into Tomcat/JBOSS webserver'
          }
        }

        stage('Unit tests') {
          steps {
            echo 'Run the JUnit tests'
          }
        }

      }
    }

    stage('SMOKE tests') {
      parallel {
        stage('SMOKE tests') {
          steps {
            echo 'Basic sanity/smoke tests'
          }
        }

        stage('GUI tests') {
          steps {
            echo 'Run the GUI tests using Selenium Webdriver'
          }
        }

        stage('Performance tests') {
          steps {
            echo 'Run the performance tests using JMeter'
          }
        }

        stage('API tests') {
          steps {
            echo 'Run the API tests using RestAssured'
          }
        }

        stage('CLI tests') {
          steps {
            echo 'Run the command line tests'
          }
        }

      }
    }

    stage('NEXUS publish') {
      steps {
        echo 'Publish the artifacts into NEXUS repository'
      }
    }

    stage('Production Release') {
      steps {
        echo 'Release into production servers'
      }
    }

  }
}