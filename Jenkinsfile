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
                     
     withCredentials([string(credentialsId: 'ubuntu-pass', variable: 'SUDO_PASS')]) {
      sh 'ansible-playbook nginx_deploy.yml -i inventory.ini --extra-vars "ansible_become_pass=$SUDO_PASS"'
}
}
}

}

}


}
