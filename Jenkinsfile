node('built-in') 
{
    stage('ContinuousDownlaod') 
    {
        git 'https://github.com/deohdeoh/maven.git'
}
    stage('ContinuousBuild') 
    {
        sh 'mvn package'
}
    stage('ContinuousDeployment') 
    {
        deploy adapters: [tomcat9(credentialsId: '7a0424aa-3491-4837-820d-08f1f3296447', path: '', url: 'http://172.31.94.233:8080')], contextPath: 'testapp', war: '**/*.war'
}
 stage('ContinuousTesting') 
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /var/lib/jenkins/workspace/ScriptedPipeline2/testing.jar'
}   
    stage('ContinuousDelivery') 
    {
        deploy adapters: [tomcat9(credentialsId: '7a0424aa-3491-4837-820d-08f1f3296447', path: '', url: 'http://172.31.81.92:8080')], contextPath: 'prodapp', war: '**/*.war'
}
}























