pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/xdossantos/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                sh 'nvm compile'
            }
        }
        stage('Test'){
            steps{
                sh 'nvm test'
            }
        }
        stage('Package'){
            steps{
                sh 'nvm package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline/target/*jar'
            }
        }
        
    }
}
