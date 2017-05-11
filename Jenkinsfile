properties([					
   pipelineTriggers([
      cron('H/2 * * * *'), //every five minutes
      pollSCM('''H 9 7-13 1 1''')
   ])
])
def rebuild = getCause()

node {
    stage('success'){ 
        print "Im the Job!"
    }
    stage('fail') {
      print "i Fail"
       if(!rebuild){ 
         bat "exit 1"
       }
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
   def result = false
   for(entry in causes) {
      print entry.getShortDescription()
      if( entry.hashCode() == 5)
      {
         result = true
      }
   }
   return result;
}
   
