pipeline{

agent any

stages{

    stage('Build') {
    agent{
        docker {
            image 'node:18-alpine'
            reuseNode true

        }
    }
    steps {
        sh '''
            # Listing the all files in the directory
	    ls -la
            node --version
            npm --version
            ls -la
        '''
    }

    }
        stage('Test') {
            agent{
        docker {
            image 'node:18-alpine'
            reuseNode true

        }
    }
            steps {
                 
                  sh  'test -f public/index.html'
                  npm test
                
            }

        }
}

}
