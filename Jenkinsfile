pipeline {
    agent {
        label 'instance-group-1-t9xm' // Replace with the label or name of your GCP instance
    }

    environment {
        GITHUB_REPO_URL = 'https://github.com/Vardaan096/gcp-repo.git' // Replace with your GitHub repo URL
        DESTINATION_DIR = '/home/vardaansharma096/git_repo/' // Replace with the desired destination directory on the instance
    }

    stages {
        stage('Clone from GitHub') {
            steps {
                script {
                    sh "git clone $GITHUB_REPO_URL $DESTINATION_DIR"
                }
            }
        }
    }
}

