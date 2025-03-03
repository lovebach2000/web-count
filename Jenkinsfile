node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/lovebach2000/web-count.git'
    }

    stage('Build image') {
       dockerImage = docker.build("barkatthemoon2024/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
