# KeycloakCertManager
Keycloak deployment with nginx TLS Termination and lets encrypt certificates

To get this helm chart running, you only need to do a couple of things:

1. install custom resource definitions: kubectl apply -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.8/deploy/manifests/00-crds.yaml
2. helm init --history-max 200
3. helm dependencies update
4. add your hostname for the tls certificate to templates/http-keycloak-ingress.yaml
5. helm upgrade --install <release name> -f values.yaml ./



Accessing the keycloak service without TLS, you need to do following:
kubectl port-forward <release name>-<chart name>-0 8080:8080

access with your browser http://localhost:8080/auth/