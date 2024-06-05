node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("gasbugs/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'harbor-cred') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
