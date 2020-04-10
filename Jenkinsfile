pipeline {
    agent {
        label 'wombat'
    } // agent
    stages {
        stage("Setup script") {
            steps {
                sh """
                    pip install pytest
                """
            } // steps
        } // stage
        stage("Run unit tests") {
            steps {
                sh """
                    python -m pytest
                """
            } // steps
        } // stage
    } // stages
    post {
        always {
            sh """
                pip uninstall -y pytest
            """
        } // always
    } // post
} // pipeline