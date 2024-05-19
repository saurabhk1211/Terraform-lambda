pipeline { 
    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }

   agent  any
    stages {
        stage('checkout') {
            steps {
                 script{
                        dir("terraform")
                        {
                            git "https://github.com/saurabhk1211/Terraform-lambda.git"
                        }
                    }
                }
            }

        stage('Plan') {
            steps {
                bat '''
                cd terraform 
                C:\\Users\\LENOVO\\OneDrive\\Desktop\\Terraform\\terraform.exe init
                '''
            }
        }
        stage('Apply') {
            steps {
                 bat '''
                cd terraform 
                C:\\Users\\LENOVO\\OneDrive\\Desktop\\Terraform\\terraform.exe apply -auto-approve
                '''
            }
        }
    }

  }
