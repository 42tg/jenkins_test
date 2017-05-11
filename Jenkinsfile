properties([					
   pipelineTriggers([
      cron('H/5 * * * *'), //ever five minutes
      pollSCM('''H 9 7-13 1 1''')
   ])
])
// Get all Causes for the current build
def causes = currentBuild.rawBuild.getCauses().properties

print causes
node {
    stage('success'){ 
        print "Im the Job!"
    }
    stage('fail') {
      print "i Fail"
       bat "exit 1"
    }
   
    stage('other')
    {
      print "i will build anyway"
    }
   
}
