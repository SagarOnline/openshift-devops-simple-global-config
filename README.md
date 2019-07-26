Commands

Create Release

1. Create Helloworld project for version V1
    
    oc new-project helloworld-v1

2. Run Jenkins pod inside the project

    oc new-app jenkins-ephemeral

3. Import Release Management Template,
    
    oc create -f https://raw.githubusercontent.com/SagarOnline/openshift-devops-simple-global-config/master/release/release-management-template.yaml

4. Checkout helloworld-config project
    git clone https://github.com/SagarOnline/openshift-devops-helloworld-config.git helloworld-config

5. Process Release Management Template to create release for helloworld v1
    oc process release-management-template --param-file=helloworld-config/release/release.properties