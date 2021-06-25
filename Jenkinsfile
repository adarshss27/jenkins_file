pipeline{
    agent any
    stages{
        stage('git scm'){
            steps{
                git branch: 'main', url: 'https://github.com/adarshss27/jenkins_ansible_test.git'
            }
        }
        stage('permission'){
            steps{
                sh 'chmod  -R 777 /var/lib/jenkins/workspace/pipeline_jen_ansible_1'
            }
        }
        stage('copy'){
            steps{
                sh 'scp -r /var/lib/jenkins/workspace/pipeline_jen_ansible_1/* adarsh@192.168.235.145:/home/adarsh/new_project1'
            }
        }
        stage('deploy-1'){
            steps{
                sh 'ssh adarsh@192.168.235.145 "ansible-playbook /home/adarsh/new_project1/ans_ble/gather_fact.yml"'                                                            
            }
        }
        stage('deploy-2'){
            steps{
                sh 'ssh adarsh@192.168.235.145 "ansible-playbook /home/adarsh/new_project1/ans_ble/gather_fact1.yml"'                                                            
            }
        }          
    }

}
