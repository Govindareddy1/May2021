pipeline { 
agent any 
    stages { 
        
        stage ('Build') { 
            steps{
                echo "Building"

            }
        }
 //for windows ---> bat "mvn clean install"   
        stage('Test') {
            steps {
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') 
                {
                    git 'https://github.com/Govindareddy1/May2021.git'
                   bat "mvn clean install"
                  // sh "mvn clean install"
                }
            }
        }
                
        stage('Publish Extent Report'){
            steps{
                     publishHTML([allowMissing: false,
                                  alwaysLinkToLastBuild: false, 
                                  keepAll: false, 
                                  reportDir: 'build', 
                                  reportFiles: 'TestExecutionReport.html', 
                                  reportName: 'HTML Extent Report', 
                                  reportTitles: ''])
            }
        }
        
        
        
    }

 }
