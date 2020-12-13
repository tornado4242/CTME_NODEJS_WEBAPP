node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {

        def customImage = docker.build("tornado4242/ctme_node_js_webapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
