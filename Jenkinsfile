def list
def stnoofstage
def noofstage

pipeline {
    agent none
    options {buildDiscarder(logRotator(daysToKeepStr: '7', numToKeepStr: '1'))}
    stages {
        stage('Create List') {
            steps {
	             
                script {
				    list = []
				    stnoofstage = '${param.no-of-stages}'
	                noofstage = stnoofstage.toInteger()
					for(int i=0; i < no-of-stage; i++) {
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