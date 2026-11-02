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
                sh 'sudo docker network rm avi_network || true'
                su 'sudo docker kill s1_con || true'
                su 'sudo docker rm s1_con || true'
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
