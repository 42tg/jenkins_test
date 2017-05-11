properties([					
   pipelineTriggers([
      cron('H/2 * * * *'), //every five minutes
      pollSCM('''H 9 7-13 1 1''')
   ])
])
getCause()

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

@NonCPS
def getCause(){
   // Get all Causes for the current build
   def causes = currentBuild.rawBuild.getCauses()
 
   
   for(entry in causes) {
      print entry.getShortDescription()
      print entry.hashCode()
   }
}
   
