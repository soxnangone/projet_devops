pipeline {
    agent any
    environment {
        DOCKER_COMPOSE_VERSION = '1.29.2'
        PATH = "/usr/local/bin:$PATH" // Assurez-vous que cela inclut le chemin vers Docker
    }
    stages {
        stage('Build') {
            steps {
                script {
                    bat 'docker --version' // Vérifier que Docker est accessible
                    // Lancement de Docker Compose
                    bat 'docker-compose up -d --build'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Mettez ici vos commandes pour exécuter des tests
                    echo "Running tests"
                    bat 'curl -s http://localhost:8000'
                }
            }
        }
        stage('Test Deploy') {
            steps {
                steps {
                withCredentials([file(credentialsId: 'kubeconfig', variable: 'KUBECONFIG')]) {
                    script {
                        // Déployer sur Kubernetes
                        bat 'kubectl apply -f mysql-deployment.yml --kubeconfig=${KUBECONFIG} --validate=false '
                        bat 'kubectl apply -f php-deployment.yaml --kubeconfig=${KUBECONFIG} --validate=false'
                        bat 'kubectl apply -f php-service.yaml --kubeconfig=${KUBECONFIG} --validate=false'
                    }
                script {
                    // Mettez ici vos commandes pour déployer l'application
                    echo "Deploy"
                }
            }
        }
    }
    post {
        success {
            // Nettoyer les ressources Docker
            bat 'docker-compose down -v'
            emailext body: 'Resultat du build: Success', subject: 'Detail du Build', to: 'ngeuya58@gmail.com'

        }
        failure {
            emailext body: 'Resultat du build: Echec', subject: 'Detail du Build', to: 'ngeuya58@gmail.com'
        }
    }
}
