# KeycloakCertManager
Keycloak deployment with nginx TLS Termination and lets encrypt certificates

To get this helm chart running, you only need to do three things:

1. helm dependencies update
2. add your hostname for the tls certificate to templates/http-keycloak-ingress.yaml
3. helm upgrade --install <release name> -f values.yaml ./



Accessing the keycloak service without TLS, you need to do following:
kubectl port-forward <release name>-<chart name>-0 8080:8080

access with your browser http://localhost:8080/auth/