node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {

        def customImage = docker.build("tornado4242/microservices-node-todo-frontendp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
