pipeline
{
    agent any
    stages
    {
    stage('Testing')
        {
            steps
            {
                script
                {
                    try
                    {
                      git 'https://github.com/intelliqittrainings/functionaltesting.git'
               sh 'java -jar /home/ubuntu/.jenkins/workspace/DeclarativePipeline/testing.jar'
                    }
                    catch(Exception e4)
                    {
                    mail bcc: '', body: 'Download fail ', cc: '', from: '', replyTo: '', subject: 'Download fail', to: 'git.testing@gmail.com'
                    exit(1)
                    }
                }

            }
       }
       }
