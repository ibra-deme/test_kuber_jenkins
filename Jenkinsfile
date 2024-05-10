pipeline {
    agent any

    environment {
        // Définir les variables d'environnement nécessaires, par exemple les informations d'authentification Kubernetes
        KUBECONFIG = credentials('kubernetes_token') // ID des credentials de Kubernetes
    }

    stages {
        stage('Checkout') {
            steps {
                // Étape pour récupérer le code source depuis un système de contrôle de version comme Git
                git 'https://github.com/ibra-deme/test_kuber_jenkins.git'
            }
        }

        // stage('Build') {
        //     steps {
        //         // Étape pour construire votre application, par exemple un Dockerfile
        //         sh 'docker build -t votre-image .'
        //     }
        // }

        // stage('Push') {
        //     steps {
        //         // Étape pour pousser votre image Docker vers un registre, par exemple Docker Hub
        //         withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials-id', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
        //             sh 'docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD'
        //             sh 'docker push votre-utilisateur/votre-image'
        //         }
        //     }
        // }

        stage('Deploy') {
            steps {
                // Étape pour déployer votre application sur Kubernetes
                bat 'kubectl get po'
            }
        }
    }
}
