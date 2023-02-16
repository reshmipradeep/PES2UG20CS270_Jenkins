pipeline 
{
  agent any
   stages 
   {
    stage('Build') 
    {
      steps 
      {
        sh 'g++ main/new.cpp -o output'
        build 'PES2UG20CS270-1'
        echo 'PES2UG20CS270 - Build Stage Successful'
      }
    }
    stage('Test') 
    {
      steps
      {
        sh './output'
        echo 'PES2UG20CS270 - Test Stage Successful'
      }
    }
    stage('Deploy') 
    {
       when 
      {
        expression 
        {
          currentBuild.result == null || currentBuild.result == 'SUCCESS' 
        }
      }
      steps 
      {
        echo 'PES2UG20CS270 - Deployment Successful'
      }
  }
  post 
  {
    failure
    {
      echo 'PES2UG20CS270 - Pipeline failed'
    }
  }
}      
}
