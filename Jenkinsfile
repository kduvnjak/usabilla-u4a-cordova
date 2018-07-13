node('mac') {
    stage('Checkout') {
        checkout scm
    }
    if (env.BRANCH_NAME == 'master') {
        stage('Release') {
            withCredentials([usernamePassword(credentialsId: '8d5dd22d-45c2-4dbd-b935-83c46df592c2', passwordVariable: 'GH_TOKEN', usernameVariable: 'JENKINS_USER')]) {
                withCredentials([usernamePassword(credentialsId: 'sdk-npm-token', passwordVariable: 'NPM_TOKEN', usernameVariable: 'NPM_USER')]) {
                    sh 'npm run semantic-release || true'
                }
            }
        }
    }
}