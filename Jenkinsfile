pipeline {
    agent any  // Runs on any available Jenkins agent

    environment {
        // Define any environment variables here, if necessary
        JAVA_HOME = '/opt/java/openjdk'
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('clone') {
            steps {
                // Checkout the Java code from the GitHub repository
                sh '''
				rm -rf jenkinjava
				git clone https://github.com/kkpant75/jenkinjava.git
				'''
            }
        }

        stage('Compile') {
            steps {
                // Compile the Java code using javac
                script {
                    // Assuming your Java code is in the 'src' directory
                    sh '''
					cd jenkinjava;
					javac HelloFromJenkin.java
					'''  // Adjust path to your Java files
                }
            }
        }

        stage('Run') {
            steps {
                // Run the compiled Java program
                script {
                    // Assuming HelloFromJenkin.class is generated in the 'src' folder
                    sh '''
					cd jenkinjava;
					java  HelloFromJenkin
					'''
                }
            }
        }
    }

    post {
        success {
            echo "Build and run successful!"
        }

        failure {
            echo "Build or run failed!"
        }
    }
}
