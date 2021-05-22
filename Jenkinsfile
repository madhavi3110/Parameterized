pipeline {
	agent any
		stages{
				stage('Set up parameters'){
					steps {
						Script {
							properties([
							parameters([
							choice(
							choices: ['Dev', 'Test'], 
							description: 'in NF1 brnach Dev and Test', 
							name: 'NF1'
							), 
						   choice(
						   choices: ['Dev', 'Test'], 
						   description: '', 
						   name: 'NF2')
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
