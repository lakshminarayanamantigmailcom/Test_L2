pipeline {
    agent {label 'JDK'}
    parameters {
        choice(name: 'BRANCH', choices: ['main', 'lucky', 'lucky_sr'], description: 'select your branch')
        choice(name: 'MVNgoals', choices: ['package', 'install', 'clean install', 'deploye'], description: 'select your task')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git',
                branch: "${prams.BRANCH}"
            }
        }
        stage('build') {
            steps {
                sh "${prams.MVNgoals}"
            }
        }
    }
}
