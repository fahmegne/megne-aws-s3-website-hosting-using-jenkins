pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }      
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-east-1',credentials:'Jenkins-cred') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'frankafashion.link')
                         s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'components.html', bucket:'frankafashion.link')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.bc58148c.js.gz', bucket:'frankafashion.link')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'assets', bucket:'frankafashion.link')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'sample', bucket:'frankafashion.link')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.bc58148c.js', bucket:'frankafashion.link')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.bc58148c.map', bucket:'frankafashion.link')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.d8e0d294.css', bucket:'frankafashion.link')
                       s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'main.d8e0d294.css.gz', bucket:'frankafashion.link')
                       
                     
                  }
              }
         }
     }
}
