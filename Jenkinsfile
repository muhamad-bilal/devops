pipeline {
agent any
stages {
stage('Checkout') {
steps {
git branch: 'main', url: 'https://github.com/muhamad-bilal/devops'
}
}
stage('Build Docker Image') {
steps {
sh 'docker build -t python-app .'
}
}
stage('Deploy to Kubernetes') {
steps {
sh 'kubectl apply -f deployment.yaml'
}
}
}
post {
success {
echo 'Pipeline succeeded!'
}
failure {
echo 'Pipeline failed!'
}
}
}
