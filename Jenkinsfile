#!groovy
stage 'clone_load_dev_n_mod'
node {
    // first repository
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'subdirectory1']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/BitwiseInc/developer-module.git']]])
    // second repository
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'subdirectory2']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/exorcist007/ModeratorModule.git']]])
    // run first script
    load 'subdirectory1/Jenkinsfile'
    // run second script
    load 'subdirectory2/Jenkinsfile'
}