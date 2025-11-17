pipeline{
	agent any
	stages{
        stage('Descargar repositorio') { 
            steps {
				        git url: 'https://github.com/darrsal/primerJAVA.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'javac Hola.java'
            }
        }
        stage('Ejecuta') {
            steps {
                sh 'java Hola'
            }
        }
        stage('Despliegue'){
            steps {
				sh 'jar cf Hola.jar Hola.class'
                archiveArtifacts artifacts: '*.jar', fingerprint: true
            }
        }
	}
}
