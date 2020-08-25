def list
//ef stnoofstage
def noofstage

pipeline {
    agent none
    options {buildDiscarder(logRotator(daysToKeepStr: '7', numToKeepStr: '1'))}
    stages {
        stage('Create List') {
            steps {
	             
                script {
				    list = []
				    noofstage = '${params.no-of-stages}'
	                //noofstage = stnoofstage.toInteger()
					for(int i=0; i < noofstage; i++) {
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