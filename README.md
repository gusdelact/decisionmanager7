# decisionmanager7
Instrucciones:

oc new project decisionmanager7
#image stream 
oc create -f rhdm70-image-streams.yaml 
#templates
oc create -f rhdm70-full.yaml
oc create -f rhdm70-kieserver.yaml
oc create -f rhdm70-kieserver-basic-s2i.yaml
oc create -f rhdm70-kieserver-https-s2i.yaml
#secretos
oc create -f decisioncentral-app-secret.yaml 
oc create -f kieserver-app-secret.yaml 
#aplicacion
sh -x crear.sh

oc get pods -w
