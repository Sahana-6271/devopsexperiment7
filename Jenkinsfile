pipeline{
  agent any
  stages{
     stage('Checkout'){
      steps{
        checkout scm
      }
    }
    stage('Build'){
      steps{
        echo 'Checking python Application'
        bat 'python -m py compile app.py'
      }
    }
    stage('Test'){
      steps{
        echo 'Excecuting automated tests'
        bat 'python -m py unittest app'
      }
    }
    stage('Run Application'){
      steps{
        bat 'python app.py'
      }
    }
  }

  post{
    success{
      echo 'CI pipeline completed sucessfully'
    }
    failure{
      echo 'CI pipeline failed'
    }
  }
}
