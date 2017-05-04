properties([		
   parameters([
      string(defaultValue: 'Hello Moto', description: '', name: 'hello')
   ]),
   pipelineTriggers([
      //cron('H H/2 * * *'),
      pollSCM('''H 9 7-13 1 1''')
   ])
])

node {
   print "Im the branch Job!"
   
   print "And know some Parameters: ${env.hello}"
}
