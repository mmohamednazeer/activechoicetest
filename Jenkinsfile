properties([parameters([[$class: 'CascadeChoiceParameter', choiceType: 'PT_SINGLE_SELECT', filterLength: 1, filterable: false, name: 'DockerFileSelected', randomName: 'choice-parameter-245681220765408', referencedParameters: '', script: [$class: 'GroovyScript', fallbackScript: [classpath: [], sandbox: false, script: ''], script: [classpath: [], sandbox: false, script: '''def fileList = [\'/bin/bash\', \'-c\', "git clone --single-branch --branch ActiveChoiceJenkins https://github.com/smartimran003/kubernetesGrafanaESApp.git > /dev/null 2>&1 ; cd git ; ls -d */ | cut -f1 -d\'/\' "].execute()
fileList.waitFor()
return fileList.text.readLines()''']]]])])




stage 'Init'
node {
  checkout scm
  sh 'echo $BRANCH_NAME'
}
if (env.BRANCH_NAME == 'main') {
  stage 'Only on master'
  println 'This happens only on master'
} else {
  stage 'Other branches'
  println "Current branch ${env.BRANCH_NAME}"
}

println "${DockerFileSelected}"
