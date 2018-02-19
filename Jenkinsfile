pipeline {
  agent {
    node {
      label 'TEST'
    }
    
  }
  stages {
    stage('prepare') {
      steps {
        echo 'Preparing test pipeline'
        jiraGetIssue(idOrKey: 'PACK-902', failOnError: true)
        svn(poll: true, url: 'http://nexus.netia.org:8081/nexus/content/repositories/clarify-snapshots/pl/netia/sws/sws-app/3.77.Blowhole-SNAPSHOT/sws-app-3.77.Blowhole-20180219.152457-22.ear')
        sh '''cd $JBOSS_HOME/server/sws/deplloy
ls -la'''
      }
    }
  }
}