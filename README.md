### To learn CI/CD using Jenkins in Docker with Pipelines

### 1. **Setting Up Jenkins Using Docker**
   - **Install Jenkins**: 
		
		docker-compose up --build
	
   - **Validate Docker**: You can see below
	 
     - docker images
		
	jenkins/jenkins                           lts                                                                           01ccf53ac680   2 weeks ago     779MB
		
     - docker ps -a 

		jenkins/jenkins:lts        "/usr/bin/tini -- /u…"   32 hours ago   Up 5 minutes                 0.0.0.0:50000->50000/tcp, 0.0.0.0:8090->8080/tcp   jenkins

   - **Start Jenkins**: After installation 
     - Visit Jenkins UI at http://localhost:8090 (this port you can change in docker-compose.yaml file)

   - **Install Plugins**: Jenkins is extensible, and many plugins are required for various integrations. For pipelines, the **Pipeline plugin** should be installed.


### 4. **Running a Pipeline in Jenkins**
   1. **Create a Jenkins Job**:
      - Go to the Jenkins dashboard and click on "New Item".
      - Choose "Pipeline" and name it.
      - Under the pipeline section, point to your repository and specify the path to the `Jenkinsfile`.

   2. **Run the Pipeline**: Once you have configured your pipeline job, you can trigger it manually or automatically through a commit to your repository (if integrated with version control like GitHub, Bitbucket, or GitLab).

   3. **Monitor the Pipeline**: After starting the pipeline, Jenkins will display the progress in each stage of the pipeline. You can monitor logs and check for errors directly from the Jenkins UI.


   - **Triggers**: You can set triggers like GitHub webhook integration or time-based triggers for running pipelines automatically when a push happens to your repository or on a scheduled basis.
