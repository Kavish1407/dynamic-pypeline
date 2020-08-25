def list
pipeline {
    agent none
    options {buildDiscarder(logRotator(daysToKeepStr: '7', numToKeepStr: '1'))}
    stages {
        stage('Create List') {
            steps {
	
                script {
                    // you may create your list here, lets say reading from a file after checkout
					for(int i=0; i < ${params.no-of-stages}; i++) {
                     list.add("Test-".concat($i))  
					 echo list
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