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
							description: 'Choose the app env to deploy', 
							name: 'Environemnt'
							), 
						   choice(
						   choices: ['NF1', 'NF2', 'NF3', 'NF4], 
						   description: 'Choose the branch to deploy', 
						   name: 'Branch')
						   ])
						   ])
						}
					}
				}
				stage('Deploy to Development') {
					when {
						expression { 
							return params.Environemnt == 'Dev' 
						}
					}
					steps {
							sh """
							echo "deploy to ${params.deployEnv}"
							"""
					}
				}
				stage('Deploy to Test') {
					when {
						expression { 
							return params.Environemnt == 'Test'
						}
					}
					steps {
						script {
							sh """
							echo "deploy to ${params.deployEnv}"
							"""
							}
					}
            }
		}
}
