pipeline {
    agent none

    stages {
        stage('Non Parallel Execution') {
            agent {
                label "master"
            }
            steps {
                echo 'This stage will run first'
            }
        }
        
        stage('parallel Execution') {
            parallel {
                stage ('Run on master') {
                    agent {
                        label "master"
                    }
                    steps {
                        echo "Running on master"
                    }
                }
                
                stage ('Run on agent') {
                    agent {
                        label 'Linux_Node'
                    }
                    steps {
                        echo 'Running on agent'
                    }
                }
            }
        }
    }
}
