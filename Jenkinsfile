stage('Dependency Check') {
    steps {
        dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
    }
}

stage('Code Analysis') {
    steps {
        sh 'sonar-scanner'
    }
}

