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
        bat 'python -m py_compile Test.java'
      }
    }
    stage('Test'){
      steps{
        echo 'Excecuting automated tests'
        bat 'python -m unittest Test'
      }
    }
    stage('Run Application'){
      steps{
        bat 'python Test.java'
      }
    }
  }

  post{
    success{
      echo 'CI pipeline completed successfully'
    }
    failure{
      echo 'CI pipeline failed'
    }
  }
}
