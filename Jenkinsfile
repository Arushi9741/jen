pipeline{
    agent any
    stages{
        stage('git clone'){
            steps{
                git credentialsId : 'todaytoken', url : 'https://github.com/Arushi9741/jen.git', branch : 'main'
            }
        }

        stage('dependency'){
            steps{

                echo "dependent file"
                bat " " "
                python -m venv venv
                call venv\\Scripts\\activate
                python -m pip install --upgrade pip
                pip install pytest
                " " "
            }
        }
        stage('test'){
            steps{

                echo "testing stage"
                bat " " "
                call venv\\Scripts\\activate
                pytest test.py
                " " "
            }
        }
        stage('deploy'){
            steps{

                echo "deployment"
                bat " " "
                call venv\\Scripts\\activate
                python stack.py
                " " "
            }
        }
    }
}



