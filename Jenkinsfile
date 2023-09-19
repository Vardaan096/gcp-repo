pipeline {
    agent any

    environment {
        GCP_INSTANCE_1_IP = '104.199.205.46'
        GCP_INSTANCE_2_IP = '34.80.149.170'
        GITHUB_REPO_URL = 'https://github.com/Vardaan096/gcp-repo.git'
    }

    stages {
        stage('Clone from GitHub') {
            steps {
                script {
                    // Clone the GitHub repository into the first instance
                    sshagent(['67b5c8e6-3a9d-40d9-b59e-d4a9da8b0c51']) {
                        sh """
                        ssh -o StrictHostKeyChecking=no -i ~/.ssh/id_rsa 104.199.205.46 \
                            "git clone ${env.GITHUB_REPO_URL} /home/vardaansharma096/git_repo/"
                        """
                    }

                    // Clone the GitHub repository into the second instance
                    sshagent(['67b5c8e6-3a9d-40d9-b59e-d4a9da8b0c51']) {
                        sh """
                        ssh -o StrictHostKeyChecking=no -i ~/.ssh/id_rsa 34.80.149.170 \
                            "git clone ${env.GITHUB_REPO_URL} /home/vardaansharma096/git_repo/"
                        """
                    }
                }
            }
        }
    }
}

