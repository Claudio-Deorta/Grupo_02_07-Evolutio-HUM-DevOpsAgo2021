pipeline {
  agent any
  stages {
    stage('Construyendo la app') {
      steps {
        echo '"Construyendo la app"'
      }
    }

    stage('Construccion ambiente desarrollo back') {
      steps {
        sh 'ambiente_desarollo_back'
      }
    }

    stage('construccion ambiente desarollo front') {
      steps {
        sh 'ambiente_desarollo_front.sh'
      }
    }

    stage('Ambiente QA') {
      steps {
        sh 'ambiente_qa.sh'
      }
    }

    stage('Aprobacion manual ') {
      steps {
        echo '"esperando por aprobacion manual"'
        input 'Estata todo ok para desplegar '
        timestamps() {
          echo 'Momento de confirmacion del ok manual '
        }

      }
    }

    stage('Despliege') {
      steps {
        echo '"desplige a produccion"'
        sh 'despliege.sh'
      }
    }

  }
}
