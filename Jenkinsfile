pipeline {
    agent {
        label 'wombat'
    } // agent
    stages {
        stage("Setup script") {
            steps {
                sh """
                    pip3 install pytest
                """
            } // steps
        } // stage
        stage("Run unit tests") {
            steps {
                sh """
                    python3 -m pytest
                """
            } // steps
        } // stage
    } // stages
    post {
        always {
            sh """
                pip3 uninstall -y pytest
            """
        } // always
    } // post
} // pipeline