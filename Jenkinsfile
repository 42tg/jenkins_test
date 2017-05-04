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
        build '42tg-second', parameters: [string(name: 'hello', value: 'I was started by Master')]
    }
}
