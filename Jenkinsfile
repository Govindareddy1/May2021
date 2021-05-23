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
                    bat "mvn clean install"
                  
                }
            }
        }
                
        stage('Publish Extent Report'){
            steps{
                     publishHTML([allowMissing: false,
                                  alwaysLinkToLastBuild: false, 
                                  keepAll: false, 
                                  reportDir: 'TestReport', 
                                  reportFiles: 'Automation Test Results.html', 
                                  reportName: 'HTML Extent Report',  
                                  reportTitles: ''])
            }
        }
        
        
        
    }

 }
