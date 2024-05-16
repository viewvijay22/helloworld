node{
    def mavenHome = tool name: 'maven3.96'
    stage ('code checkout')
            {
                git credentialsId: 'b5e7b194-eba5-495c-b627-b903d7a67224', url: 'https://github.com/viewvijay22/helloworld.git'
            }
    stage ( 'maven build' )
       sh "$mavenHome/bin/mvn clean install"
    stage ( 'codequalityanalysis' )
       sh "$mavenHome/bin/mvn sonar:sonar"
    stage ( 'nexus artifactory upload' )
       sh "$mavenHome/bin/mvn deploy"   
}
