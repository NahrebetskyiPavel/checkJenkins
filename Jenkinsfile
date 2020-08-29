pipeline {
    agent any
    options {
        parallelsAlwaysFailFast()
    }
    stages {
        stage('Non-Parallel Stage') {
            steps {
                echo $MYVARNAME_USR
            }
        }
        stage('Parallel Stage') {
            when {
                branch 'master'
            }
            parallel {
                stage('Branch A') {
                    agent {
                        label "ubuntu"
                    }
                    steps {
                        echo "ubuntu"
                    }
                }
                stage('Branch B') {
                    agent {
                        label "ubuntu"
                    }
                    steps {
                        echo "ubuntu"
                    }
                }
                stage('Branch C') {
                    agent {
                        label "ubuntu"
                    }
                    stages {
                        stage('Nested 1') {
                            steps {
                                echo "In stage Nested 1 within Branch C"
                            }
                        }
                        stage('Nested 2') {
                            steps {
                                echo "In stage Nested 2 within Branch C"
                            }
                        }
                    }
                }
            }
        }
    }
}
