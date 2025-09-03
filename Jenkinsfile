pipeline {
    agent any

    stages {
        stage('Pull Code') {
            steps {
                git branch: 'main', url: 'https://github.com/bk-thakur/jenkins-nginx-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "✅ Build step - nothing to build for static site"
            }
        }

        stage('Deploy') {
            steps {
                echo "🚀 Deploying to Nginx..."
                sh '''
                sudo rm -rf /usr/share/nginx/html/*
                sudo cp -r * /usr/share/nginx/html/
                sudo systemctl restart nginx
                '''
            }
        }
    }
}
