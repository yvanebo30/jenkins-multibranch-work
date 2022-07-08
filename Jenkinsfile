pipeline{
  agent any
  stages{
  	stage('version-control'){
  		steps{
  			checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/etechDevops/team2-multibuild.git']]])
  		}
  	}
    stage('parallel-job'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'action1'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action2'
          }
        }
      }
    }
    stage('codebuild'){
    	steps{
    		sh 'cat /etc/passwd'
    	}
    }
  }
}