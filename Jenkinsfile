pipeline{
      agent { label 'slave_one' }
      stages{
      stage('check out'){
                  steps{
                  sh "rm -rf hello-world-war"
                  sh "git clone https://github.com/Sagar1895/hello-world-war.git"
                  }
                  }
      stage('build'){
      steps{
      sh "pwd"
      sh "ls"
      sh "cd hello-world-war"
      sh "docker build -t sagar8123onkar/sagarnewrepo:1.1 ."
      }
      }
       stage('publish'){
                  steps{
                        sh "docker login -u sagar8123onkar -p Sagaronkar@96"
                        sh "docker push sagar8123onkar/sagarnewrepo:1.1"
                  }
            }
            stage('deploy'){
                  agent { label 'slave_two' }
                  steps{
                        sh "docker login -u sagar8123onkar -p Sagaronkar@96"
                        sh "docker pull sagar8123onkar/sagarnewrepo:1.1"
                        //sh "docker rm -f trail1"
                        sh "docker run -d -p 8080:8080 --name trail1 sagar8123onkar/sagarnewrepo:1.1"
                  }
            }
      }
      }
