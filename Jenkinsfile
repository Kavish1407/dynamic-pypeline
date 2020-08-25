def list
pipeline {
    agent none
    options {buildDiscarder(logRotator(daysToKeepStr: '7', numToKeepStr: '1'))}
    stages {
        stage('Create List') {
            steps {
	
                script {
					for(int i=0; i < no-of-stages; i++) {
                     list.add("Test $i")
                    }
                }
            }
        }
        stage('Dynamic Stages') {
            steps {
                script {
                    for(int i=0; i < list.size(); i++) {
                        stage(list[i]){
                            echo "Element: $i"
                        }
                    }
                }
            }
        }
    }
}