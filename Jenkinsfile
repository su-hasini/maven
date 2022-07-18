@Library('mylibrary')_
pipeline
{
    agent any
    stages
    {
        stage('Continuous Download')
        {
            steps
            {
                script
                {
                  cicd.newGit("https://github.com/su-hasini/maven.git")
                }
            }
        }
        stage('ContinuousBuild')
        {
            steps
            {
                script
                {
                    cicd.newMaven()
                }
            }    
        }
        stage('conti.deploy')
        {
            steps
            {
                script
                {
                    cicd.newDeploy("sharedlibrarywithdeclarativepipeline","172.31.86.200","testapp")
                }
            }
        }
        stage('conti.Testing')
        {
            steps
            {
                script
                {
                    cicd.newGit("https://github.com/su-hasini/functionaltesting.git")
                    cicd.runSelenium("sharedlibrarywithdeclarativepipeline")
                }
            }
        }
        stage('conti.delivery')
        {
            steps
            {
                script
                {
                    cicd.newDeploy("sharedlibrarywithdeclarativepipeline","172.31.86.63","prodapp")
                }
            }
        }
    }
}
