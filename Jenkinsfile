node{
    
    stage('Clone repo'){
        git credentialsId: 'GIT-Credentials', url: 'https://github.com/shailajakalai/mavenrepo.git'
    }
    
    stage('SonarQube analysis') {
    def scannerHome = tool 'sonar-server';
    withSonarQubeEnv('sonar-server') {
      sh "${scannerHome}/bin/sonar-scanner \
      -D sonar.login=admin \
      -D sonar.password=admin123 \
      -D sonar.projectKey=sonarqubetest \
      -D sonar.exclusions=vendor/**,resources/**,**/*.java \
      -D sonar.host.url=http://54.249.129.77:9000/"
    }
  }
}
