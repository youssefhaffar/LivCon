pipeline
{
		agent any
 		  stages
 		  {
			stage('Pull')
			{
				steps{
					script{
						checkout([$class: 'GitSCM' , branches: [[name: '*/master']],
							userRemoteConfigs : [[
								credentialsId: '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',
								url: 'https://github.com/youssefhaffar/LivCon.git']]])
					      }
				     }
			}
			stage('docker')
			{
				steps {
					script{
					sh " sudo -S ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml "
						}
					}			
			}
			stage('Build')
			{
				steps {
					script{
					sh " sudo -S ansible-playbook ansible/build.yml -i ansible/inventory/host.yml "
						}
					}			
			}
			
			
			
		}
}
