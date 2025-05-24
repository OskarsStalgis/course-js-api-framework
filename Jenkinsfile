pipeline {
    agent any
    triggers{
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-api-test-img') {
            steps {
                buildDockerImg()
            }
        }
    }
}

def buildDockerImg(){
    echo "Building of node application is starting.."
    sh "docker build -t oskarsstalgis/api-tests ."

    echo "Pushing img to Docker registry.."
    sh "docker push oskarsstalgis/api-tests"
}
