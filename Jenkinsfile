properties([					
   pipelineTriggers([
      cron('H/2 * * * *'), //every five minutes
      pollSCM('''H 9 7-13 1 1''')
   ])
])

def rebuild = getCause()

node {
   stage ('checkout'){
//checkout changelog: false, scm: scm
checkout(
	[
		$class: scm.$class,
		additionalCredentials: scm.additionalCredentials,
		browser: [
			$class: 'FishEyeSVN',
			rootModule: '',
			url: 'https://jira-sf.starfinanz.de/fisheye/browse/SVN_SFirm/'
		],
		excludedCommitMessages: scm.excludedCommitMessages,
		excludedRegions: scm.excludedRegions,
		excludedRevprop: scm.excludedRevprop,
		excludedUsers: 'batch',
		filterChangelog: scm.filterChangelog ,
		ignoreDirPropChanges: scm.ignoreDirPropChanges,
		includedRegions: scm.includedRegions,
		locations: scm.locations,
		workspaceUpdater: scm.workspaceUpdater,
		changelog: false
	])
   }
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
   
