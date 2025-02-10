@Library('Shared')_
pipeline{
    agent { label 'dev-server'}
    
    stages{
        stage("Code clone"){
            steps{
                sh "whoami"
            clone("https://github.com/Aryankumar-crypto/django-notes-app.git","main")
                echo ("cloning done....")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("notes-app","latest")
                echo ("build done..")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","notes-app","latest")
                echo ("push done....")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
