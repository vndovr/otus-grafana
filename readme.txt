# Add repository for ingress

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

# Install prometheus & grafana 

helm install prom -f prom.yaml prometheus-community/kube-prometheus-stack
helm install nginx ingress-nginx/ingress-nginx -f ing.yaml

# Start container

helm install oc ./otus-container

# Uninstall all

helm uninstall oc
helm uninstall nginx 
helm uninstall prom
