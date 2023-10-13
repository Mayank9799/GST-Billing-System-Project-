pipeline {
  agent{
        label "jenkins-agent"
    }
        

  stages {

    stage("Deploy to GCP-VM"){
      steps {
        echo 'Deploy release to testing'
        script {
            
            
                    try{
                       // replace image and tag    
                                           
                       sh """
                       echo "we have implemented new changes today at 12.30" > Mayank2.txt
                       """
                        // Fill the slack message with the success message
                        textMessage = "Deployment Successfull"
                        inError = false 

                    } catch(e) {

                        echo "$e"
                        // Fill the slack message with the fail message
                        textMessage = "Deployment failed"
                        inError = true

                    } finally {

                        // Send Slack notification with the result of the tests
                        sh"""
                            curl -X POST -H 'Content-type: application/json' --data '{"text":"${textMessage}"}' https://hooks.slack.com/services/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
                        """ 
                        if(inError) {
                          // Send an error signal to stop the pipeline
                          error("Failed deployment")
                        }  
                         
                    }
              }
            
        }
      }
    

  }

}
