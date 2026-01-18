pipeline {
    agent any
    
    parameters {
        string(
            name: 'TERRAFORM_PATH',
            defaultValue: './terraform',
            description: 'Шлях до Terraform-коду'
        )
        booleanParam(
            name: 'AUTO_APPROVE',
            defaultValue: false,
            description: 'Прапорець для auto-apply'
        )
        choice(
            name: 'ENVIRONMENT',
            choices: ['dev', 'stage', 'prod'],
            description: 'Оточення (dev, stage, prod)'
        )
    }
    
    stages {
        stage('Checkout') {
            steps {
                echo "Checking out code..."
                checkout scm
            }
        }
        
        stage('Backup Jenkins Home') {
            steps {
                echo "Бекап Jenkins Home"
                echo "Branch: ${env.BRANCH_NAME}"
                echo "Build: ${env.BUILD_NUMBER}"
                echo "Environment: ${params.ENVIRONMENT}"
                echo "Terraform Path: ${params.TERRAFORM_PATH}"
                echo "Auto Approve: ${params.AUTO_APPROVE}"
                sh '''
                    echo "Creating Jenkins home backup..."
                    echo "This is a placeholder for backup logic"
                '''
            }
        }
    }
    
    post {
        always {
            echo "Pipeline completed for branch: ${env.BRANCH_NAME}"
        }
    }
}

