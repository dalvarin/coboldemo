pipeline {
    agent any

    stages {
        stage('Init Cobol Environment') {
            steps {
                echo 'Hello World'
                sh '. /opt/microfocus/EnterpriseDeveloper/bin/cobsetenv'
                sh 'export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64'
                sh 'export PATH=$PATH:/usr/lib/jvm/java-11-openjdk-amd64/bin'
                sh 'export ANT_OPTS=-Xmx512m'
            }
        }
        stage('Build'){
            steps{
                sh 'ant -lib $COBDIR/lib/mfant.jar -f .cobolBuild'
            }
        }
    }
}