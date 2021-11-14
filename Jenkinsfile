pipeline
{
		agent any
 		  stages{
			stage('Pull'){
				steps{
					script{
						checkout([$class: 'GitSCM' , branches: [[name: '*/master']],
							userRemoteConfigs : [[
								credentialsId: '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',
								url: 'https://github.com/youssefhaffar/LivCon.git']]])
					      }
				     }
				      }			
			}
}
