pipeline
{
    agent any

    stages 
	{
        stage('Build') 
		{
            steps 
			{
                echo 'Build App..'
            }
        }
		
		stage('Test') 
		{
            steps 
			{
                echo 'Test App.....'
            }
        }
		
		stage('Deploy') 
		{
            steps 
			{
                echo 'Deploy World'
            }
        }
		
    }
	
	post 
	{
        always 
		{
           emailext body: 'Test pipeline', subject: 'Jenkins Pipeline Automation', to: 'agreddytest@gmail.com'
        }
    }
}
