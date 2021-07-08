pipeline {
    agent any

    stages {
        stage('Init Cobol Environment') {
            steps {
                script {
                    . /opt/microfocus/EnterpriseDeveloper/bin/cobsetenv
                    export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.292.b10-1.el7_9.x86_64/
                    export PATH=$PATH:/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.292.b10-1.el7_9.x86_64/bin
                    export ANT_OPTS=-Xmx512m
                    ant -f .cobolBuild
                }
            }
        }
        stage('Store'){
            steps{
                archiveArtifacts "New_Configuration.bin/Coboldemo"
            }
        }
    }
}
