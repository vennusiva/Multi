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
        stage('Delivery')
        {
            steps
            {
                script
                {
                    try
                    {
                     deploy adapters: [tomcat9(credentialsId: '7a85843d-77ba-453a-b51d-5ee9fe622849', path: '', url: 'http://172.31.93.21:8080')], contextPath: 'Prod', war: '**/*.war'
                    }
                    catch(Exception e5)
                    {
                        mail bcc: '', body: 'Download fail ', cc: '', from: '', replyTo: '', subject: 'Download fail', to: 'git.delivary@gmail.com'
                        exit(1)
                    }
                }

            }
        }
    }
}
