pipeline {
    agent any  
    stages {
        stage("test") {
            steps {
                echo "hello world"
            }
        }
        stage("build") {
            steps {
                script {
                    bat 'docker --version'
                   // bat "docker-compose up -d --build"
                }
            }
        }
        /*stage("deploy to Kubernetes") {
            steps {
                withCredentials([file(credentialsId: 'configuration1', variable: 'KUBECONFIG')]) {
                    script {
                        // Déployer sur Kubernetes
                        bat "kubectl apply -f kubernetes/mysql-deployment.yml --kubeconfig=${KUBECONFIG} --validate=false"
                        bat "kubectl apply -f kubernetes/php-deploy.yaml --kubeconfig=${KUBECONFIG} --validate=false"
                        bat "kubectl apply -f kubernetes/php-service.yaml --kubeconfig=${KUBECONFIG} --validate=false"
                    }
                }
            }*/
            stage('Deploiement sur Terraform') {
            steps {
               bat 'terraform init'
               bat 'terraform plan'
               bat 'echo "yes" | terraform apply -auto-approve'
                //sh 'minikube service php-service'
            }

           }
        }
    }
    post {
        success {
            emailext (
                subject: "Notification de build Jenkins - Succès",
                body: "Le build de votre pipeline Jenkins s'est terminé avec succès.",
                to: "snac2214@gmail.com",
            )
        }
        failure {
            emailext (
                subject: "Notification de build Jenkins - Échec",
                body: "Le build de votre pipeline Jenkins a échoué.",
                to: "snac2214@gmail.com",
            )
        }
    }
}
