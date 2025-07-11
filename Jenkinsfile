node {
    def mavenHome = tool name: 'maven'
    stage('checkout') {
        // Checkout source code from SCM (Git)
        git credentialsId: 'git', url: 'https://github.com/viewvijay22/helloworld.git'
    }
    stage('Build') {
        sh "$mavenHome/bin/mvn clean install"
    }
    stage('sonarqubeanalysis') {
        sh "$mavenHome/bin/mvn sonar:sonar"
    }
    stage('nexusstage') {
        sh "$mavenHome/bin/mvn deploy"
    }
}

