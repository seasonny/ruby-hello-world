This is a sample openshift v3 application repository.  

For instructions on how to use it, please see: https://github.com/openshift/origin/blob/master/examples/sample-app/README.md


```bash

oc login -u user -p your-password

oc new-project my-custom --display-name='My custom assemble script project' --description="An explanation"

oc new-app https://github.com/<yourname>/ruby-hello-world --image-stream=ruby:2.3 --name='my-custom-builder-test'

# watch the build logs
oc logs my-custom-builder-test-1-build -f

# Sample Output
---> Installing application source ...
---> Building your Ruby application from source ...
[...]
Bundled gems are installed into ./bundle.
---> Cleaning up unused ruby gems ...
---> CUSTOM S2I ASSEMBLE COMPLETE
Pushing image docker-registry.default.svc:5000/my-custom/my-custom-builder-test:latest ...
[...]
Push successful

oc status
oc get all

```
