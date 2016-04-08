

properties [
  [
    $class: 'ParametersDefinitionProperty', parameterDefinitions: [
      [
        $class: 'ChoiceParameterDefinition', choices: ['plan', 'apply'], description: 'When this job is invoked directly, action that TF will perform', name: 'tf_action'
      ],
      [
        $class: 'GitParameterDefinition', branch: '', branchFilter: '.*', defaultValue: 'master', description: 'Branch to use for plan when this job is invoked directly. This is ignored and always "master" when tf_action is apply', name: 'git_branch', quickFilterEnabled: true, sortMode: 'ASCENDING_SMART', tagFilter: '*', type: 'PT_BRANCH'
      ]
    ]
  ]
]


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
