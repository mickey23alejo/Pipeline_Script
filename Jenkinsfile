pipeline {
   agent none
	//agent any
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "principal"
                }
        steps {
                echo 'This stage will be executed firs'
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    steps {
			sleep 10
			java -jar JavaSimple.jar
                        echo "Task1 on Parallel"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        //label "mock"
			label "principal"
                    }
                    steps {
			    	sleep 10
				echo "Task2 on Parallel"
			}
                }
            }
        }
    }
}
