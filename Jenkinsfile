
// https://github.com/jenkinsci/pipeline-examples/blob/master/pipeline-examples/get-build-cause/getBuildCause.groovy

def causes = currentBuild.rawBuild.getCauses()

println causes.dump()
println causes
causes = ''

PRCause   = currentBuild.rawBuild.getCause(org.jenkinsci.plugins.github.pullrequest.GitHubPRCause)
SCMCause  = currentBuild.rawBuild.getCause(hudson.triggers.SCMTrigger$SCMTriggerCause)
UserCause = currentBuild.rawBuild.getCause(hudson.model.Cause$UserIdCause)



if (PRCause) {

  println PRCause.properties

} else if (SCMCause) {

  println SCMCause.properties

} else if (UserCause) {

  println UserCause.properties

} else {
  error 'This job cant be triggered however it was just triggered, sorry.'
}

PRCause   = null
SCMCause  = null
UserCause = null
