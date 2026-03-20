pipeline { 
    agent any

    stages {
	
        stage('CLONE GITHUB CODE') {
            steps {
                echo 'In this stage code will be cloned'
                git branch: 'main', credentialsId: 'git-creds', url: 'https://github.com/priyankayadav-911/3-ansible-docker-project.git'
            }
        }
		
        // stage('BUILDING THE CODE') {
        //     steps {
        //         echo 'In this stage code will be built and mvn artifact will be generated'
        //         sh 'mvn clean install'
        //     }
        // }		
		
        stage('DEPLOY WITH ANSIBLE') {
            steps {
                sh '''
                    ansible-playbook playbook.yml 
                '''
            }
        }
    }
}
