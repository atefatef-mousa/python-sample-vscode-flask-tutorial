
// // declarative pipeline syntax

// pipeline{
//     agent{
//         label "agent_1"
//     }
//     environment{
//         XYZ='ITI ITI ITI'
//     }
//     stages{
//         stage("build Docker image"){
//             steps{
//                 sh "docker build -t itiv4/data-iti:v${BUILD_NUMBER} ."
//             }
//         }
//         stage("Push Docker image"){
//             steps{
//                 sh "docker tag itiv4/data-iti:v${BUILD_NUMBER} atefmousa/data-iti:v${BUILD_NUMBER}"
//                 sh "docker push atefmousa/data-iti:v${BUILD_NUMBER}"
//             }
//         }
//     }
// }



// // // scripted pipeline syntax

node('agent_1') {
    env.XYZ = 'ITI ITI ITI'
    
    stage("Build Docker Image") {
        sh "docker build -t itiv4/data-iti:v${BUILD_NUMBER} ."
    }
    
    stage("Push Docker Image") {
        sh "docker tag itiv4/data-iti:v${BUILD_NUMBER} atefmousa/data-iti-scripted-way:v${BUILD_NUMBER}"
        sh "docker push atefmousa/data-iti-scripted-way:v${BUILD_NUMBER}"
        }
}
