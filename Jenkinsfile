pipeline {
    agent none
    stages {
	
	stage('Non-Parallel Stage') {
	    agent {
                        label "master"
                }
        steps {
                echo 'This stage will be executed first'
		sleep 10
                }
        }

	
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                   agent {
                        label "pedo"
                    }
                    steps {
                        echo "Task1 on Parallel"
			    sleep 10
                    }
                    
                }
                stage('Test On Master') {
                    agent {
                        label "madcool"
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
