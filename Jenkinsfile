pipeline {
  agent any
  stages{
    
      stage ('install modules'){
       steps{
        bat '''
          yarn add
        '''
      }
    }
    
    
      stage ('code quality'){
       steps{
        bat '''
          $(npm bin)/ng lint
          
         '''
       }
      }
    
    stage ('build') {
      steps{
        bat '''
            $(npm bin)/ng build --prod --build-optimizer
         '''
      }
    }

    stage('Archive') {
      steps{
        bat ''''
            tar -cvzf dist.tar.gz --strip-components=1 dist
            archive 'dist.tar.gz'
            
           '''
      }
        
    } 
  }
}
