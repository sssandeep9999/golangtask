# Assignment

- Write a statefulset/Deployment to deploy the docker image built in docker task. 

- Use configMap/Secret for all the env variables used in the ecomapp

- Create service and ingress object to route traffic to both microservices

## Advance:

- Configure oauth2-proxy authentication in both the services. Try to setup oauth2-proxy with github/azure/keycloak, any OIDC provider

- Configure tls on the ingress object using cert-manager operator  