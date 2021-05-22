pipeline {
	agent any
		stages{
				stage('Set up parameters'){
					steps {
						script {
							properties([
							parameters([
							choice(
							choices: ['Dev', 'Test'], 
							description: '', 
							name: 'Environemnt'
							), 
						   choice(
						   choices: ['NF1', 'NF2'], 
						   description: '', 
						   name: 'Branch')
						   ])
						   ])
						}
					}
				}
				stage('Deploy to Development') {
					when {
						expression { 
							return params.ENVIRONMENT == 'Dev' 
						}
					}
					steps {
                    sh """
                    echo "deploy to Dev"
                    """
                }
            }
				stage('Deploy to Test') {
					when {
						expression { 
							return params.ENVIRONMENT == 'Test'
						}
					}
					steps {
                    sh """
                    echo "deploy to Test"
                    """
                }
            }
		}
}
