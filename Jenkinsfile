pipeline{
    agent{
        label{
            label "built-in"
        }
    }
    stages{
        stage('clean'){
            steps{
                echo 'clean'
            }
        }
        stage('build'){
            steps{
                echo 'build'
                echo 'pwd'
                echo 'whoami'
                sh 'ansible-playbook playbook.yaml'
            }
        }
        stage('deploy'){
            steps{
                echo 'deploy'
            }
        }
    }
}
