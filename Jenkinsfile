#!groovy 

node {
   wrappers {
   	nodejs('NodeJS 4.4.5')
  }
   stage 'Checkout'
        checkout scm

   stage 'Mocha test'
        sh './node_modules/mocha/bin/mocha'

   stage 'Cleanup'
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
}
