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
                       echo "Hello Mayank Sir" > Mayank.txt
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
