pipeline {
   //agent none
	agent any
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
		    agent {
                        label "principal"
                    }
                    steps {
			sleep 4
			bat "java -jar JavaSimple.jar"
                        echo "Task1 on Parallel"
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "mock"
                    }
                    steps {
			    	sleep 4
				echo "Task2 on Parallel"
			}
                }
            }
        }
    }
}
