pipeline {
    agent any  // 选择任何可用的Jenkins节点执行

    stages {
        stage('Checkout') {
            steps {
                // 拉取GitHub上的代码
                git 'https://github.com/nippon1218/mgroovy.git'
            }
        }

        stage('Run HelloWorld') {
            steps {
                script {
                    // 执行HelloWorld.groovy脚本
                    def groovyScript = load 'HelloWorld.groovy'
                    groovyScript.run()
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline execution succeeded.'
        }
        failure {
            echo 'Pipeline execution failed.'
        }
    }
}
