node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', 
            url: 'https://github.com/suhan1433/breeds-classification.git'
    }

    stage('Build image') {
        script {
            dockerImage = docker.build("suhan123/web_count:v1.0")
        }
    }

    stage('Push image') {
        script {
            withDockerRegistry([credentialsId: 'docker-access', url: '']) {
                dockerImage.push()
            }
        }
    }
}

