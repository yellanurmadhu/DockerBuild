node
	{
		stage('Build Docker Build')
			{
			    
				sh 'VERSION=$(date+%H-%M-%S)'
				sh 'docker build -t yellanurmadhu/lab:${VERSION}'		
			}
			
		stage('Push Image to Docker Hub')
		    {
			sh 'dokcer push yellanurmadhu/lab${VERSION}'
			}
		stage('Deploy Image in Docker Container')
		    {
			#sh 'docker -H tcp://10.1.1.100:2375 stop nginx'
			#sh 'docker -H tcp://10.1.1.100:2375 run --rm -dit -p 8000:80 -name nginx --hostname nginx yellanurmadhu/lab:${VERSION}' 
			
				sh 'docker -H  stop nginx'
			sh 'docker -H  run --rm -dit -p 8000:80 -name nginx --hostname nginx yellanurmadhu/lab:${VERSION}'
		
			}
	}
	
