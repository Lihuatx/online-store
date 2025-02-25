pipeline {
    agent any

    stages {
        stage('pull source code') {
            steps {
                git branch: 'main', credentialsId: 'github_Lihuatx', url: 'https://github.com/Lihuatx/online-store.git'
            }
        }
        stage('build source') {
            steps {
                sh '''echo "运行 npm install"
                npm install
                echo "运行 npm run build"
                npm run build
                cp -r ./dist/* /docker/nginx/data/html/
                echo "构建成功"'''
            }
        }
    }
}
