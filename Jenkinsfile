def imageName = 'skyglass/bank-online-ui'
def registry = 'https://registry.hub.docker.com'

node('workers'){
    def imageTest

    stage('Checkout'){
        checkout scm
    }

    stage('Build & Push'){
        echo '=== Packaging Petclinic Application ==='
        docker.withRegistry(registry, 'dockerHubCredentials') {
            imageTest.push("latest")  
        }
    }
   
}