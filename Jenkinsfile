properties([					
   pipelineTriggers([
      //cron('H H/2 * * *'),
      pollSCM('''H 9 7-13 1 1''')
   ])
])
// Get all Causes for the current build
def causes = currentBuild.rawBuild.getCauses()

print causes.getShortDescription();
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
