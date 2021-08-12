
stage 'Init'
node {
  checkout scm
  sh 'echo $BRANCH_NAME'
  sh 'echo $CHANGE_ID'
  print("Change ID: "+env.CHANGE_ID)
}
if (env.BRANCH_NAME == 'main') {
  stage 'Only on master'
  println 'This happens only on master'
} else {
  stage 'Other branches'
  println "Current branch ${env.BRANCH_NAME}"
}

println "hello"
