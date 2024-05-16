/*pipeline {
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
        stage("deploy to Kubernetes") {
            steps {
                withCredentials([file(credentialsId: 'configuration1', variable: 'KUBECONFIG')]) {
                    script {
                        // Déployer sur Kubernetes
                        bat "kubectl apply -f kubernetes/mysql-deployment.yml --kubeconfig=${KUBECONFIG} --validate=false"
                        bat "kubectl apply -f kubernetes/php-deploy.yaml --kubeconfig=${KUBECONFIG} --validate=false"
                        bat "kubectl apply -f kubernetes/php-service.yaml --kubeconfig=${KUBECONFIG} --validate=false"
                    }
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
}*/

pipeline {
    agent any
    environment {
        // Assurez-vous que ce chemin mène à votre kubeconfig local généré par Minikube
        KUBECONFIG = "C:/Users/Ngoné NIANG SARR/.kube/config"
        // Chemin où se trouvent vos fichiers Terraform dans votre projet
        TERRA_DIR = "C:/xampp/htdocs/projet_fil_rouge-main/Terraform"
    }
    stages {
        stage('Initialization') {
            steps {
                // Affiche la version de Terraform pour le débogage
                script {
                    bat 'terraform --version'
                }
            }
        }
        
        stage("Terraform Init") {
            steps {
                script {
                    // Initialise Terraform
                    bat "cd %TERRA_DIR% && terraform init"
                }
            }
        }
        
        stage("Terraform Plan") {
            steps {
                script {
                    // Exécute le plan Terraform
                    bat "cd %TERRA_DIR% && terraform plan"
                }
            }
        }
        
        stage("Terraform Apply") {
            steps {
                script {
                    // Applique la configuration Terraform
                    bat "cd %TERRA_DIR% && terraform apply --auto-approve"
                }
            }
        }
    }
    post {
        always {
            script {
                // Nettoie l'environnement après l'exécution du pipeline
                bat "cd %TERRA_DIR% && terraform destroy --auto-approve"
            }
        }
        succes {
            emailext (
                subject : "Notification de build de jenkins avec terraform-succes",
                body : "votre build de pipeline jenkins terraform passe avec succes",
                to : "snac2214@gmail.com"
            )
        }
        failure {
            emailext (
                subject : "Notification de build de jenkins avec terraform echec",
                body : "votre build de pipeline jenkins ne passe pas",
                to : "snac2214@gmail.com"
            )
        }
    }
}