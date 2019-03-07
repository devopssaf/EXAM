node {
  stage ('Clone Repository') {
  checkout scm
      }
  stage ('Build a Docker Image'){
  sh "docker build -t kago_exam:1.0 ."
  }
  stage ('Push Image to Docker Hub'){
  sh "docker login -u 'gideonkago' -p 'Kitale12345' "
  sh "docker tag kago_exam:1.0 gideonkago/kago_exam:1.0"
  sh "docker push gideonkago/kago_exam:1.0"
  }
  stage ('Deploy Docker Image'){
  sh "docker container run --detach --publish 1280:80 --name kago_exam_2 gideonkago/kago_exam:1.0"
  }
}
