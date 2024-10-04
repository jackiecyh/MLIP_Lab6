pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                
                # Create the virtual environment if it does not exist
                if [ ! -d "mlip" ]; then
                    python3 -m venv mlip
                fi

                # Ensure the activate script is executable
                chmod +x mlip/bin/activate
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: We run testing tool like pytest here'

                # TODO fill out the path to conda here
                source mlip/bin/activate
                echo 'Past path'
s
                # TODO Complete the command to run pytest
                pip install pytest
                mlip/bin/activate run -n mlip pytest
                echo 'Past run'

                echo 'pytest not runned'
                exit 1 #comment this line after implementing Jenkinsfile
                '''

            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our porject'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
