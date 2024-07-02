pipeline {
    agent any
    environment {
        //JAVA_HOME = 'C:\\Program Files\\Java\\jdk1.8.0_202'
        //PYTHON_HOME = 'C:\\Users\\ouldache\\AppData\\Local\\Programs\\Python\\Launcher\\'
       // PATH = "${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}"
	 PATH="${env.PATH}:/usr/bin"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/mertilm/jenkins-data-pipeline.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'echo "Running on Unix"'
			//sh 'apt install python3-pip'
			//sh 'apt install python3.11-venv'
			//sh 'sudo python3 -m venv myenv'
			//sh 'cd ./myenv/bin/activate '
			//sh 'ls'
			sh 'source myenv/bin/activate'
			sh 'pip install pandas'
		      	sh 'python3 data_analysis.py'
                    } else {
                        
                        bat 'echo "Running on Windows"'
                       // bat 'virtualenv temp'
                       // bat './temp/Scripts/acivate.bat'
                       // bat 'python'
                       // bat 'pip install -r requirements.txt'
                       // bat 'python data_analysis.py'  

                    }
                }
            }
        }
    }
}
