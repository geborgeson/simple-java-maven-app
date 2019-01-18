pipeline {
	Agent {
		Docker {
			image 'maven:3-alpine'
			args '-v /root/.m2:/root/.m2
		}
	}
	Stages {
		stage('Build'){
			steps {
				sh 'mvn -B -DskipTests clean package'
			}
		}
	}
}
	