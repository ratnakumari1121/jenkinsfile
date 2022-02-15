node 
{
    stage('GIT clone'){	 
     git branch: 'main', credentialsId: 'git-passwd', url: 'https://github.com/ratnakumari1121/dec2021.git'
}
    stage ('maven clear'){
            sh ''' mvn clean'''
}
    stage ('maven validate'){
            sh '''mvn validate'''
}
    stage ('maven compile'){
            sh '''mvn compile'''
}
    stage ('maven test'){
            sh '''mvn test'''	
} 
    stage('maven package') {
            sh '''mvn package'''
} 
}
