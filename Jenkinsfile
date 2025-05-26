
@Library('global_lib_x')_


// // declarative pipeline syntax

pipeline{
    agent{
        label "agent_1"
    }
    environment{
        DOCKER_USER = credentials('dockerhub-user')
        DOCKER_PASS = credentials('dockerhub-password')
    }
    stages{
        stage("build Docker image"){
            steps{
                script{
                    def dockerx = new org.iti.docker()
                    dockerx.build("python_build", "${BUILD_NUMBER}")
                    // sh "docker build -t itiv4/data-iti:v${BUILD_NUMBER} ."
                }
            }
 
               
            
        }
        stage("Push Docker image"){
            steps{
                script{
                    def dockerx = new org.iti.docker()
                    dockerx.login("${DOCKER_USER}", "${DOCKER_PASS}")
                    dockerx.push("python_build","${DOCKER_USER}", "${BUILD_NUMBER}")
                }
                // sh "docker tag itiv4/data-iti:v${BUILD_NUMBER} atefmousa/data-iti:v${BUILD_NUMBER}"
                // sh "docker push atefmousa/data-iti:v${BUILD_NUMBER}"
            }
        }
    }
}



// // scripted pipeline syntax

// node('agent_1') {
//     env.XYZ = 'ITI ITI ITI'
    
//     stage("Build Docker Image") {
//         sh "docker build -t itiv4/data-iti:v${BUILD_NUMBER} ."
//     }
    
//     stage("Push Docker Image") {
//         sh "docker tag itiv4/data-iti:v${BUILD_NUMBER} atefmousa/data-iti-scripted-way:v${BUILD_NUMBER}"
//         sh "docker push atefmousa/data-iti-scripted-way:v${BUILD_NUMBER}"
//         }
// }
