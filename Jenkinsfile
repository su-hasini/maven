@Library('mylibrary')_
pipeline
{
    agent any
    stages
    {
        stage('Continuous Download_test')
        {
            steps
            {
                script
                {
                  cicd.newGit("https://github.com/su-hasini/maven.git")
                }
            }
        }
        stage('ContinuousBuild_test')
        {
            steps
            {
                script
                {
                    cicd.newMaven()
                }
            }    
        }
    }
}
