pipeline {
	agent any
	
	stages {
	
		stage('Build Application') {
			steps {
			
					bat 'mvn clean install'

					}

									}
		stage('Test') {
			steps {

					echo 'Application in Testing Phase…'
					bat 'mvn test'

					}

						}

		stage('Deploy CloudHub') {
		
					environment {

ANYPOINT_CREDENTIALS = credentials('anypoint.credential')

}

					steps {

						echo 'Deploying mule project due to the latest code commit…'
						
						echo 'Deploying to the configured environment….'
						
						bat 'mvn clean deploy -DmuleDeploy -Dusername=${ANYPOINT_CREDENTIALS_USR} -Dpassword=${ANYPOINT_CREDENTIALS_PSW} -DworkerType=Micro -Dworkers=1 -Dregion=us-west-2'

							}

						}

					}

				}