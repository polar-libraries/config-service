custom_build(
    # Name of the container image
    ref = 'config-service',

    # Command to build the container image do container
    command = './gradlew bootBuildImage --imageName $EXPECTED_REF',

    # Arquivos a serem observados que acionam uma novam compilação
    deps = ['build.gradle', 'src']
)

#Deployment
k8s_yaml(['k8s/deployment.yml', 'k8s/service.yml'])
#ManagePort
k8s_resource('config-service', port_forwards=['8888'])