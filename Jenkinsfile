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
                sh '''
                    ansible devlinux -b -m shell -a "docker rm -f s1_con || true"
                    ansible devlinux -b -m community.docker.docker_network -a "name=avi_network state=absent"
                '''
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
