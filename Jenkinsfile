pipeline {
  agent any
	triggers{
	pollSCM '* * * * *'
	
}
  parameters {
    gitParameter branchFilter: 'origin/(.*)', defaultValue: 'null', name: 'BRANCH', type: 'PT_BRANCH'
  }
  stages {
    stage('Clone') {
      steps {
        git poll: true, branch: "${params.BRANCH}", url: 'https://github.com/karthick626590/mywork.git'

      }
    }
    stage('shell script'){
	steps {
          sh 'sh test.sh'
	}
      }
    stage('Testing the branch name'){
        steps {
          echo scm.branches[0].name.split("/")[1]
        }
      }

  }
}
