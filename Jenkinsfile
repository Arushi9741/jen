pipeline{
    agent any
    stages{
        stage('git clone'){
            steps{
                git url "https://github.com/Arushi9741/jen.git".branch : "main"
            }
        }

        stage('dependency'){
            steps{

                echo "dependent file"
                bat ' ' '
                python -m venv venv
                call venv\\Scripts\\active
                python -m pip install --upgrade pip
                pip install pytest
                ' ' '
            }
        }
        stage('test'){
            steps{

                echo "testing stage"
                bat ' ' '
                call venv\\Scripts\\active
                pytest test.py
                ' ' '
            }
        }
        stage('deploy'){
            steps{

                echo "deployment"
                bat ' ' '
                call venv\\Scripts\\active
                python stack.py
                ' ' '
            }
        }
    }
}



