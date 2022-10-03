pipeline{
   agent( "any" )
     stages {
       steps {
         step( "cloning git repo" ) {
           "git 'https://github.com/grootsadmin/groots_node_sample_frontend'"
         }
         step( "build with maven" ) {
            sh "mvn clean package"
         }
         step( "create docker image" ) {
            sh "docker build -t frontendapp ."
         }
         step( "run docker container" ) {
             sh "docker run -d -p 80:80 frontendapp sample"
         }
       } 
     }
}
