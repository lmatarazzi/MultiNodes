pipeline {
    agent { label 'Win-Slave' }
	stages {
    		stage('Git Checkout') {
			try {
		    	// notify via slack that a build has started
            		notifyBuild('STARTED Checkout ...')
		    	checkout scm	
	       		notifyBuild('DONE Checkout!')		
			} catch(e) {
           			currentBuild.result = "Checkout failed"
            			notifyBuild(currentBuild.result)
            			throw e
       			}
    		}
	}
}
