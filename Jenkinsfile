pipeline {
  
  // Lab 0
  // this just verifies the basics, can we build an image correctly
  
  environment {
    //
    // this should be fairly unique, it doesn't need to be perfect
    // since we're not going to push this anywhere
    //
    IMAGE = "${JOB_BASE_NAME}:${BUILD_NUMBER}"
  } // end environment
  
  agent any
  stages {
    
    stage('Checkout SCM') {
      steps {
        checkout scm
      } // end steps
    } // end stage "checkout scm"

    stage('Install and Verify Tools') {
      steps {
        sh '''
          ### if docker isn't available, just bail 
          ### (correcting this is a bigger problem outside the scope of this workshop)
          which docker   
        '''
      } // end steps
    } // end stage "install and verify tools"
    
    stage('Build image and tag with build number') {
      steps {
        sh '''
          docker build --network=host -t ${IMAGE} .
        '''  
      } // end steps
    } // end stage "build image and tag w build number"  

  } // end stages

} //end pipeline
