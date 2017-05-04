properties([					
   pipelineTriggers([
      //cron('H H/2 * * *'),
      pollSCM('''H 9 7-13 1 1''')
   ])
])

node {
   print "Im the Job!"
}
