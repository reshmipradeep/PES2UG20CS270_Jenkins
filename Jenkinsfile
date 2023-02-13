pipeline 
{
  agent any
   stages 
   {
    stage('Build') 
    {
      steps 
      {
        sh 'mvn clean install'
        echo 'PES2UG20CS270 - Build Stage Successful'
        sh 'chmod +x new.sh'
        sh 'new.sh
      }
    }
    stage('Test') 
    {
      steps
      {
        sh 'mvn test'
        echo 'PES2UG20CS270 - Test Stage Successful'
        post 
        {
          always 
          {
            junit 'target/surefire-reports/*.xml'
          }
        }
      }
    }
    stage('Deploy') 
    {
      steps 
      {
        sh 'mvn deploy'
        echo 'PES2UG20CS270 - Deployment Successful'
      }
    }
  }
  post 
  {
    failure
    {
      echo 'PES2UG20CS270 - Pipeline failed!'
    }
  }
}      
