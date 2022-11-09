node {
  stage("Hello") {
    print "Hi!"

    if (params.commit_sha?.trim()) {
      print "Checking out commit ${commit_sha}"

      scmVars = checkout([
        $class: 'GitSCM',
        branches: [[name: params.commit_sha]],
      ])
    } else {
      print "Checking out master"

      scmVars = checkout(scm)
    }
  }
}
