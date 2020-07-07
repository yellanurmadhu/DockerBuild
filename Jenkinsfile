node
	{
		stage('Build Docker Build')
			{
			    
				sh 'VERSION=$(date +%H-%M-%S)'
				sh 'docker build -t yellanurmadhu/lab:${VERSION}'		
			}
			
		stage('Push Image to Docker Hub')
		    {
			sh 'dokcer push yellanurmadhu/lab${VERSION}'
			}
		stage('Deploy Image in Docker Container')
		    {
					
				sh 'docker -H  stop nginx'
			sh 'docker -H  run --rm -dit -p 8000:80 -name nginx --hostname nginx yellanurmadhu/lab:${VERSION}'
		
			}
	}
	
