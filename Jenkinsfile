properties([					
   pipelineTriggers([
      cron('1 * * * *'), //every five minutes
      pollSCM('''H 9 7-13 1 1''')
   ])
])
// Get all Causes for the current build
def causes = currentBuild.rawBuild.getCauses()
def specificCause = currentBuild.rawBuild.getCause(hudson.model.Cause$UserIdCause)

print specificCause.getShortDescription()

for(entry in causes) {
   print entry.getShortDescription();
}
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
