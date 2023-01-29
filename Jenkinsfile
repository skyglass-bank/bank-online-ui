def imageName = 'skyglass/bank-online-ui'
def registry = 'https://registry.hub.docker.com'

node('workers'){
    def app

    stage('Checkout'){
        checkout scm
    }

    stage('Build Docker Image') {
        when {
            branch 'master'
        }
        steps {
            echo '=== Building Petclinic Docker Image ==='
            script {
                app = docker.build(imageName)
            }
        }
    }    

    stage('Push Docker Image'){
        echo '=== Packaging Petclinic Application ==='
        docker.withRegistry(registry, 'dockerHubCredentials') {
            app.push("latest")
        }
    }
   
}