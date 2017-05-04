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
    input 'Ready to go?'
    stage('other')
    {
        build(job: '42tg-second', parameters : [hello : 'I was started by Master'])
    }
}
