pipeline {

 agent any
 stages {

  stage("git"){
   steps {
    git branch: "main", url: "https://github.com/sohail-24/ansible-pipeline-day26.git"
}

}
  stage("ansible") {
   steps {
    sshagent(credentials: ["vm-ssh-key"]) {
     sh "ansible-playbook nginx_deploy.yml -i inventory.ini"
}

}

}

}


}
