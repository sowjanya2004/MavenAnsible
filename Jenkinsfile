pipeline{
agent any

tools{
maven 'Maven'
}

stages{
stage('Checkout'){
steps{
git branch:'master',url:'https://github.com/sowjanya2004/MavenAnsible.git'

}
}

stage('Build'){
steps{
sh 'mvn clean package'
}
}

stage('Archive'){
steps{
archiveArtifacts artifacts:'target/*.war',fingerprint:true
}
}

stage('Deploy'){
steps{
sh 'mvn clean package'
sh 'ansible-playbook playbook.yml -i hosts.ini'
}
}
}
}
