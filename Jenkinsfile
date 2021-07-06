pipeline {
    agent any

    stages {
        stage('Init Cobol Environment') {
            steps {
                echo 'Hello World'
                sh '. /opt/microfocus/EnterpriseDeveloper/bin/cobsetenv'
                sh 'export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.292.b10-1.el7_9.x86_64/'
                sh 'export PATH=$PATH:/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.292.b10-1.el7_9.x86_64/bin'
                sh 'export ANT_OPTS=-Xmx512m'
                sh 'ant -lib $COBDIR/lib/mfant.jar -f .cobolBuild'
            }
        }
        stage('Build'){
            steps{
                sh 'ant -lib $COBDIR/lib/mfant.jar -f .cobolBuild'
            }
        }
    }
}
