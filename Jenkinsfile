pipeline {
    agent any
    environment {
        // Définissez ici le chemin d'accès à kubeconfig et au répertoire Terraform
        KUBECONFIG = "C:\\Users\\Ngoné NIANG SARR\\.kube\\config"
        TERRA_DIR = "C:\\xampp\\htdocs\\projet_fil_rouge-main\\Terraform"
        // Assurez-vous que ce chemin pointe vers l'emplacement de l'exécutable Terraform sur la machine Jenkins
        TERRAFORM_PATH = "C:\\terraform"
    }
    stages {
        stage("Test") {
            steps {
                echo "Hello, World!"
            }
        }
        stage("Build") {
            steps {
                script {
                    bat 'docker --version'
                    // Commentez la ligne suivante si docker-compose n'est pas nécessaire
                    // bat "docker-compose up -d --build"
                }
            }
        }
        /*
        stage("Deploy to Kubernetes") {
            steps {
                script {
                    // Déployer sur Kubernetes en utilisant kubectl si nécessaire
                    // Commentez ou supprimez cette section si vous ne l'utilisez pas
                }
            }
        }
        */
        stage('Déploiement avec Terraform') {
            steps {
                bat "cd %TERRA_DIR% && terraform init"
                bat "cd %TERRA_DIR% && terraform plan"
                bat "cd %TERRA_DIR% && terraform apply -auto-approve"
            }
        }
    }
    post {
        success {
            emailext (
                subject: "Notification de Build Jenkins - Succès",
                body: "Le build de votre pipeline Jenkins s'est terminé avec succès.",
                to: "snac2214@gmail.com"
            )
        }
        failure {
            emailext (
                subject: "Notification de Build Jenkins - Échec",
                body: "Le build de votre pipeline Jenkins a échoué.",
                to: "snac2214@gmail.com"
            )
        }
        // Vous pouvez également ajouter d'autres notifications ou actions post-build si nécessaire
    }
}
    stages {
        stage("Test") {
            steps {
                echo "Hello, World!"
            }
        }
        stage("Build") {
            steps {
                script {
                    bat 'docker --version'
                    // Commentez la ligne suivante si docker-compose n'est pas nécessaire
                    // bat "docker-compose up -d --build"
                }
            }
        }
        /*
        stage("Deploy to Kubernetes") {
            steps {
                script {
                    // Déployer sur Kubernetes en utilisant kubectl si nécessaire
                    // Commentez ou supprimez cette section si vous ne l'utilisez pas
                }
            }
        }
        */
        stage('Déploiement avec Terraform') {
            steps {
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" init"
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" plan"
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" apply -auto-approve"
            }
        }
    }
    post {
        success {
            emailext (
                subject: "Notification de Build Jenkins - Succès",
                body: "Le build de votre pipeline Jenkins s'est terminé avec succès.",
                to: "snac2214@gmail.com"
            )
        }
        failure {
            emailext (
                subject: "Notification de Build Jenkins - Échec",
                body: "Le build de votre pipeline Jenkins a échoué.",
                to: "snac2214@gmail.com"
            )
        }
        // Vous pouvez également ajouter d'autres notifications ou actions post-build si nécessaire
    }

    stages {
        stage("Test") {
            steps {
                echo "Hello, World!"
            }
        }
        stage("Build") {
            steps {
                script {
                    bat 'docker --version'
                    // Commentez la ligne suivante si docker-compose n'est pas nécessaire
                    // bat "docker-compose up -d --build"
                }
            }
        }
        /*
        stage("Deploy to Kubernetes") {
            steps {
                script {
                    // Déployer sur Kubernetes en utilisant kubectl si nécessaire
                    // Commentez ou supprimez cette section si vous ne l'utilisez pas
                }
            }
        }
        */
        stage('Déploiement avec Terraform') {
            steps {
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" init"
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" plan"
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" apply -auto-approve"
            }
        }
    }
    post {
        success {
            emailext (
                subject: "Notification de Build Jenkins - Succès",
                body: "Le build de votre pipeline Jenkins s'est terminé avec succès.",
                to: "snac2214@gmail.com"
            )
        }
        failure {
            emailext (
                subject: "Notification de Build Jenkins - Échec",
                body: "Le build de votre pipeline Jenkins a échoué.",
                to: "snac2214@gmail.com"
            )
        }
        // Vous pouvez également ajouter d'autres notifications ou actions post-build si nécessaire
    }

    
    stages {
        stage("Test") {
            steps {
                echo "Hello, World!"
            }
        }
        stage("Build") {
            steps {
                script {
                    bat 'docker --version'
                    // Commentez la ligne suivante si docker-compose n'est pas nécessaire
                    // bat "docker-compose up -d --build"
                }
            }
        }
        /*
        stage("Deploy to Kubernetes") {
            steps {
                script {
                    // Déployer sur Kubernetes en utilisant kubectl si nécessaire
                    // Commentez ou supprimez cette section si vous ne l'utilisez pas
                }
            }
        }
        */
        stage('Déploiement avec Terraform') {
            steps {
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" init"
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" plan"
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" apply -auto-approve"
            }
        }
    }
    post {
        success {
            emailext (
                subject: "Notification de Build Jenkins - Succès",
                body: "Le build de votre pipeline Jenkins s'est terminé avec succès.",
                to: "snac2214@gmail.com"
            )
        }
        failure {
            emailext (
                subject: "Notification de Build Jenkins - Échec",
                body: "Le build de votre pipeline Jenkins a échoué.",
                to: "snac2214@gmail.com"
            )
        }
        // Vous pouvez également ajouter d'autres notifications ou actions post-build si nécessaire
    }

    stages {
        stage("Test") {
            steps {
                echo "Hello, World!"
            }
        }
        stage("Build") {
            steps {
                script {
                    bat 'docker --version'
                    // Commentez la ligne suivante si docker-compose n'est pas nécessaire
                    // bat "docker-compose up -d --build"
                }
            }
        }
        /*
        stage("Deploy to Kubernetes") {
            steps {
                script {
                    // Déployer sur Kubernetes en utilisant kubectl si nécessaire
                    // Commentez ou supprimez cette section si vous ne l'utilisez pas
                }
            }
        }
        */
        stage('Déploiement avec Terraform') {
            steps {
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" init"
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" plan"
                bat "cd %TERRA_DIR% && \"%TERRAFORM_PATH%\" apply -auto-approve"
            }
        }
    }
    post {
        success {
            emailext (
                subject: "Notification de Build Jenkins - Succès",
                body: "Le build de votre pipeline Jenkins s'est terminé avec succès.",
                to: "snac2214@gmail.com"
            )
        }
        failure {
            emailext (
                subject: "Notification de Build Jenkins - Échec",
                body: "Le build de votre pipeline Jenkins a échoué.",
                to: "snac2214@gmail.com"
            )
        }
        // Vous pouvez également ajouter d'autres notifications ou actions post-build si nécessaire
    }

