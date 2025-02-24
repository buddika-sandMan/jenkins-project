// pipeline {
//     agent any
//     // environment {
//     // //     IMAGE_NAME = 'sanjeevkt720/jenkins-flask-app'
//     // //     IMAGE_TAG = "${IMAGE_NAME}:${env.BUILD_NUMBER}"
//     // //     KUBECONFIG = credentials('kubeconfig-credentials-id')
//     //        SERVER_CREDS = credentials('server-creds')

//     // }
//     stages {

//         stage('Checkout') {
//             steps {
//                 withCredentials([usernamePassword(credentialsId: 'server-creds', usernameVariable: 'myuser', passwordVariable: 'mypassword')]) {

//                     sh '''
//                     echo "user name: ${myuser}"
//                     echo "user password: ${mypassword}"
//                     '''
//                 }

//                 // echo "my creds: ${SERVER_CREDS}"
//                 // echo "user name: ${SERVER_CREDS_USR}"
//                 // echo "user password: ${SERVER_CREDS_PSW}"

//                 git url: 'https://github.com/kodekloudhub/jenkins-project.git', branch: 'main'
//                 sh "ls -ltr"
//                 // echo "my creds: ${SERVER_CREDS}"
//                 // echo "user name: ${SERVER_CREDS_USR}"
//                 // echo "user password: ${SERVER_CREDS_PSW}""
//                 sh "pwd"
//             }
//         }
//         // stage('Setup') {
//         //     steps {
//         //         sh "pip install -r requirements.txt"
//         //     }
//         // }
//         // stage('Test') {
//         //     steps {
//         //         sh "pytest"
//         //         sh "whoami"
//         //     }
//         // }
//         // stage('Login to docker hub') {
//         //     steps {
//         //         withCredentials([string(credentialsId: 'dockerhubpwd', variable: 'dockerhubpwd')]) {
//         //         sh 'echo ${dockerhubpwd} | docker login -u sanjeevkt720 --password-stdin'}
//         //         echo 'Login successfully'
//         //     }
//         // }
//         // stage('Build Docker Image')
//         // {
//         //     steps
//         //     {
//         //         sh 'docker build -t ${IMAGE_TAG} .'
//         //         echo "Docker image build successfully"
//         //         sh "docker images"
//         //     }
//         // }
//         // stage('Push Docker Image')
//         // {
//         //     steps
//         //     {
//         //         sh 'docker push ${IMAGE_TAG}'
//         //         echo "Docker image push successfully"
//         //     }
//         // }
//         // stage('Deploy to EKS Cluster') {
//         //     steps {
//         //         sh "kubectl apply -f deployment.yaml"
//         //         echo "Deployed to EKS Cluster"
//         //     }
//         // }
//     }
// }

// Nested stages
// pipeline {
//     agent any
//     stages {
//         stage('lint and Test') {
//             stages {
//                 stage('lint') {
//                     steps {
//                         sh 'echo "linting"'
//                     }
//                 }
//                 stage('Test') {
//                     steps {
//                         sh 'echo "testing"'
//                     }
//                 }
//             }
// stage('Deploy') {
//             steps {
//                 sh 'echo "Deploying"'
//             }
//         }
//     }
// }

Parallel stages
pipeline {
    agent any
    stages {
        stage('lint and testing') {
            parallel {
                stage('lint') {
                    steps {
                        sh 'echo "linting"'
                        git url: 'https://github.com/kodekloudhub/jenkins-project.git', branch: 'main'
                    }
                }
                stage('testing') {
                    steps {
                        sh 'echo "testing"'
                        git url: 'https://github.com/kodekloudhub/jenkins-project.git', branch: 'main'
                        sh "ls -ltr"
                    }
                }
            }
        }
    }
}
            