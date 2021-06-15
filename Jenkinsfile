pipeline { 
agent any 
   
    stages { 
        
        stage ('Dev Env CI') 
         { 
            steps
            {
                echo " Dev Building"

           }
        }
       
       stage ('Test Env CI') 
         { 
            steps
            {
                echo " Test Building"

           }
        }
 //for windows ---> bat "mvn clean install"   
        stage('Test Env Smokte Suite') {
            steps {
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') 
                {
                    bat "mvn clean test -P Smokesuite -Denv=test"
                  
                }
            }
        }
       
       
        stage ('Stage Env CI') 
         { 
            steps
            {
                echo " Test Building"

           }
        }
            stage('Stage Env Smoke Suite') {
            steps {
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') 
                {
                    bat "mvn clean test -P Smokesuite -Denv=stage"
                  
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
