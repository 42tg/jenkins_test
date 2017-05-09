properties([					
   pipelineTriggers([
      //cron('H H/2 * * *'),
      pollSCM('''H 9 7-13 1 1''')
   ])
])

node {
    stage('me'){ 
        print "Im the Job!"
    }

    stage('other')
    {
      if (result.equals("SUCCESS")) {
         stage 'deploy'
         print "Test" + result
      } else {
      currentBuild.result = e2e.result
      // but continue
      }
    }
}
