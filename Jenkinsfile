currentBuild.displayName = "CAST-"+currentBuild.number
pipeline {
    agent {
        label 'linux-agent'
    }
    stages {
        stage('Application Scan'){
            steps {
                sh '''
                
                java -jar /home/ec2-user/Highlight-Automation-Command/HighlightAutomation.jar \
                --workingDir "."\
                --sourceDir "$WORKSPACE/src"\
                --skipUpload
                
                '''
            }
        }
    }
    post {
            success { 
            	echo "This pipeline is successfull!"
            }
    	    unsuccessful {
            	echo "ISSUE!!!"
            }
    	}
}
